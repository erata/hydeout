---
layout: post
published: true
excerpt_separator: <!--more-->
title: 'Java Spring Boot: Lazy Loading nesneler ve Dto Kullanimi'
categories:
  - java
tags:
  - Spring Boot
  - Hibernate
  - Lazy Loading
---
Merhabalar.

Bu yazida DTO (Data transfer Object) seklinde bilinen veri transfer nesnelerinin Spring Boot uygulamalarinda ne kadar elzem olduguna deginmeye calisacagim.

Direk somut bir örnek üzerinden meseleyi anlatmak gerekirse ilk önce projemdeki **Post**, **Category** ve **Comment** tablolari icin Entity iliskisi kurdum.

**Post Entity sinifimiz:**
````java
package blog.model;

import lombok.*;
import org.hibernate.annotations.CreationTimestamp;
import org.hibernate.annotations.GenericGenerator;
import org.hibernate.annotations.UpdateTimestamp;

import javax.persistence.*;
import javax.validation.constraints.NotBlank;
import javax.validation.constraints.Size;
import java.io.Serializable;
import java.util.*;


@Getter
@Setter
@NoArgsConstructor
@ToString(exclude = {"user", "comments", "categories"})
@EqualsAndHashCode(exclude = {"user", "comments", "categories"})
@Entity
@Table(name = "post")
public class Post implements Serializable {
    @Id
    @GeneratedValue(generator = "uuid")
    @GenericGenerator(name = "uuid", strategy = "uuid")
    @Column(columnDefinition = "CHAR(32)")
    private String id;

    @NotBlank(message = "title is mandatory")
    @Size(max = 100)
    @Column(name = "title", unique = true, nullable = false)
    private String title;

    @NotBlank(message = "content is mandatory")
    @Lob
    @Column(name = "content", nullable = false)
    private String content;

    @Column(name = "is_published")
    private Boolean isPublished = false;

    @CreationTimestamp
    @Temporal(TemporalType.TIMESTAMP)
    @Column(name = "created_at")
    private Date createdAt;

    @UpdateTimestamp
    @Temporal(TemporalType.TIMESTAMP)
    @Column(name = "updated_at")
    private Date updatedAt;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "user_id", nullable = false)
    private User user;

    @OneToMany(
            mappedBy = "post",
            fetch = FetchType.LAZY,
            cascade = CascadeType.ALL,
            orphanRemoval = true
    )
    private List<Comment> comments = new ArrayList<>();

    public void addComment(Comment comment) {
        comments.add(comment);
        comment.setPost(this);
    }

    public void removeComment(Comment comment) {
        comments.remove(comment);
        comment.setPost(null);
    }

    public void removeAllComments() {
        for (Comment comment : new ArrayList<>(comments)) {
            removeComment(comment);
        }
    }

    @ManyToMany(
            fetch = FetchType.LAZY,
            cascade = {CascadeType.PERSIST, CascadeType.MERGE}
    )
    @JoinTable(name = "post_category",
            joinColumns = @JoinColumn(name = "post_id"),
            inverseJoinColumns = @JoinColumn(name = "category_id"))
    private Set<Category> categories = new HashSet<>();

    public void addCategory(Category category) {
        categories.add(category);
        category.getPosts().add(this);
    }

    public void removeCategory(Category category) {
        categories.remove(category);
        category.getPosts().remove(this);
    }

    public void removeAllCategories() {
        for (Category category : new ArrayList<>(categories)) {
            removeCategory(category);
        }
    }

    public Post(String title, String content, User user) {
        this.title = title;
        this.content = content;
        this.user = user;
    }
}
<!--more-->

````
**Category Entity sinifimiz:**
```java
package blog.model;

import lombok.*;

import javax.persistence.*;
import javax.validation.constraints.NotBlank;
import javax.validation.constraints.Size;
import java.io.Serializable;
import java.util.HashSet;
import java.util.Set;


@Getter
@Setter
@NoArgsConstructor
@ToString(exclude = "posts")
@EqualsAndHashCode(exclude = "posts")
@Entity
@Table(name = "category")
public class Category implements Serializable {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)  
    private Integer id;

    @NotBlank(message = "name is mandatory")
    @Size(max = 50)
    @Column(name = "name", unique = true, nullable = false)
    private String name;

    @ManyToMany(fetch = FetchType.LAZY,
            cascade = {CascadeType.PERSIST, CascadeType.MERGE},
            mappedBy = "categories")
    @Setter(AccessLevel.PRIVATE)
    private Set<Post> posts = new HashSet<>();

    public Category(String name) {
        this.name = name;
    }
}
```
**Comment Entity sinifimiz:**
```java
package blog.model;

import lombok.*;
import org.hibernate.annotations.CreationTimestamp;

import javax.persistence.*;
import javax.validation.constraints.Email;
import javax.validation.constraints.NotBlank;
import javax.validation.constraints.Size;
import java.io.Serializable;
import java.util.Date;


@Getter
@Setter
@NoArgsConstructor
@ToString(exclude = "post")
@EqualsAndHashCode(exclude = "post")
@Entity
@Table(name = "comment")
public class Comment implements Serializable {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    @Column(name = "id")  
    private Integer id;

    @NotBlank(message = "name is mandatory")
    @Size(max = 50)
    @Column(name = "name", nullable = false)
    private String name;

    @NotBlank(message = "email is mandatory")
    @Size(max = 100)
    @Email
    @Column(name = "email", nullable = false)
    private String email;

    @NotBlank(message = "content is mandatory")
    @Lob
    @Column(name = "content", nullable = false)
    private String content;

    @CreationTimestamp
    @Temporal(TemporalType.TIMESTAMP)
    @Column(name = "created_at")
    @Setter(AccessLevel.PRIVATE)
    private Date createdAt;

    @ManyToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "post_id", nullable = false)
    private Post post;

    public Comment(String name, String email, String content) {
        this.name = name;
        this.email = email;
        this.content = content;
    }
}
```

Kod örneklerinden de görüldügü üzere Post tablomuz Comment tablosu ile **one-to-many** iliskisine sahip, Category tablosu ile **many-to-many** iliskisne sahip ve User ile  **many-to-one** iliskisine sahip.

Hibernate temel ayarlarinda 
- OneToMany: LAZY
- ManyToOne: EAGER
- ManyToMany: LAZY
- OneToOne: EAGER
seklinde yüklenmeye sahip([Bkz.](https://stackoverflow.com/a/26601720/2007859)). Dolayisiyla **ManyToOne** ve **OneToOne** iliskisili nesnelerine Lazy Loading uygulamak icin Entity nesne iliskisinde belirtmek gerekmektedir @ManyToOne(fetch = FetchType.LAZY) gibi.

Simdi esas mevzumuza gelecek olursak yukaridaki Entity siniflari ile olusturdugum bir projede ilk basta DTO nesnesi kullanmadan dogrudan nesneler ile islem yapmakta idim. Entity nesnesinin Controller katmaninda kullanmam ise Hibernate hatalar girdabina girmeme yol acti. LazyInitializationException hatasi bunlardan en bilinen. Bu hatayi cözmek icin alternatif bircok yol mevcut. Kimisi Entity nesne üzerinde bir takim degisiklikler yaparken kimisi application.properties dosyasina hibernate in ilkleme sorununu görece cözmek icin bazi parametreler eklemekte. Bu yazi kapsaminda ise bizim önerecegimiz yöntem DTO nesneleri kullanmak.

DTO nesneleri kullanmak bize bircok fayda saglayacaktir:
- Normalde basit sade olmasi gereken Entity nesneleri farkli amaclarla eklenen kod parcalari ile zamanla yönetilemez hale gelmektedir. Iste DTO nesnleri, Entit nesneleri üzerine eklenen farkli amacli kod parca yükünü üzerine alarak Entity nesnelerinin sade ve basit kalmasi icin birebir.
- DTO kullanimi ile Controller-Servis-Repository arasindaki iliskiyi daha bagimsiz yapma sansimiz olmakta. 
- DTO kullanimi ile Controller a istenen büyüklükte ve kücüklükte veri saglmaka oldukca basit hale gelmekte. Mesela bir apiniz var ve farkli Entity tablolarinin farkli alanlarini iceriyor. Bu is icin DTO bicilmis kaftan.
- Yillanmis projelerinizde DTO kullanmiyorsaniz veri degisikligine karsi uygulamaniz oldukca kirilgan olacaktir. Tabi sorunlari asmak her zaman mümkün olsa da harcanan isgücü ve zaman kaybi oldukca maaliyetli olma ihtimali var. 

 ![dto nesneleri.PNG]({{site.baseurl}}/assets/media/dto nesneleri.PNG)
 
 DTO kullanimi ile api ihtiyacina uygun cevabi hazirmak ve dönmek oldukca kolaylasacaktir. Tabi bunun icin Servis katmaninda Entity nesnenizden gelen verileri DTO nesnenize mapping ile aktarmak gerekecektir. Bu mapping islemi tekrar gibi gözükse de ilerleyen asamadaki farkli ihtiyaclara uygun cözümler üretmede iki de bir Entity nesnesi ile oynamanizin önünü kesecektir.
 
Benim DTO nesnesi kullanmam Hibernate hatalarina karsi esnek bir cözüm arayisi idi. DTO kullanimin Hibernate kaynakli hatalara cözüm oldugu gibi zamanla degisen ve farkli cevaplar vermesi de gerek farkli sürümlü apiler icin de güzel bir cözüm olacagini gördüm. 
 
Umarim yararli olmustur.
 
 

