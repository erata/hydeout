---
layout: post
published: true
excerpt_separator: <!--more-->
title: ' SQLServer’da Saklı Yordam (Stored Procedure) Tanımlama ve Kullanma'
redirect_from:
  - /2018/01/01/sqlserverda-sakli-yordam-stored-procedure-tanimlama-ve-kullanma/
---
Merhaba arkadaşlar. Bu yazıda veritabanı ile ilgili önemli kavramlardan birine Saklı Yordama (Stored Procedure) değineceğiz. Birçok yerde sp yani stored procedure şeklinde ifade edilen kavrama açıklık getirmeye çalışacağız.

<!--more-->

### Saklı Yordam (Stored Procedure) Nedir?

Veritabanı sorguları her seferinde tekrar tekrar yazıp çalıştırmaktansa onları veritabanına bir yordam şeklinde kaydedebilir ve adıyla çağırarak çalıştırabiliriz.

Store procedure ile dört veritabanı işlemi (select, insert, update ve delete) sorgusu, parametreli ve parametresiz sorgular oluşturulup hazır kullanım için depolanır ve gerektiğinde adıyla çağrılarak çalıştırılırlar.

Stored Procedure Kullanmanın Faydaları Nelerdir?
Stored procedure’lar veritabanı içerisinde saklandığı için güvenlik noktasında ciddi katkılar sağlar.
Stored procedure’lar bir kez oluşturulup derlenirler ve bir daha derlenmezler. Bu sayede normal sorgu çaşıltırmalarındaki sorgu çalıştırma aşamasındaki derleme ve öncesindeki evre es geçilerek büyük bir preformans sağlanmış olur (özellikle sık çekilen bir sorgu ise)
Tekrar tekrar kullanılabilirler. Bunun için adıyla çağırmak yeterlidir.
Store Procedure kullanmak yapısal bir sadelik sağlamış olur aynı zamanda.
Stored Procedure Nasıl Tanımlanır?
Store procedure yazmak çok kolay olup parametreli ve parametresiz olması durumuna göre temelde iki şekilde store procedure yazılabilir.

### 1. Parametresiz Store Procedure

**Nasıl Tanımlanır?**

create proc/procedure   <procedure adı> 
as
begin 
<sorgu komutu>
end

Örnek Kullanım:

```sql
USE AdventureWorks2008R2
GO 

CREATE PROCEDURE spPersonListele

AS
BEGIN
select FirstName,LastName from Person.Person 
END
GO
```

Tanımlanan Store Procedure ile Sorgu Yapmak İçin:

```sql
exec spPersonListele
```

### 2. Parametreli Store Procedure 

**Nasıl Tanımlanır?**

```sql
create proc/procedure   <procedure adı> 
( 
@prm1, 
@prm2  
) 
as 
begin 
<sorgu komutu>
end
```

Örnek Kullanım:

```sql
USE AdventureWorks2008R2
GO 

CREATE PROCEDURE spParametreliPersonListele
(
@ad nvarchar(50),
@soyad nvarchar(50)
)	
AS
BEGIN
select FirstName,LastName from Person.Person where FirstName=@ad and LastName=@soyad
END
GO
```

**Tanımlanan Store Procedure ile Sorgu Yapmak İçin:**

```sql
exec spParametreliPersonListele ‘Kevin’,’Adams’
```

**Stored Procedure Tanımlarken Dikkat Edilecek Hususlar**

Tanımlamış olduğunuz bir store procedure’u ikince kez tanımlamaya (create) çalışırsanız **“There is already an object named ‘Tanımladığınız Store Procedure Adı’ in the database”** şeklinde bir hata alırsınız. Yani  **store procedurler ikinci kez derlenmez**. 

Stored procedure adı önüne **usp** veya  **sp** örneki getirmek güzel adlandırma açısından iyi olacaktır.

Store Procure İle İlgili Video:

[video:http://www.dailymotion.com/video/xc9inb_stored-procedure-sakli-yordam-kulla_tech]

### Kaynaklar:

- http://www.yazilimdilleri.net/YazilimMakale-3117-SQL-Server-Stored-Procedure-Olusturulmasi-ve-Kullanimi.aspx- http://www.sqlogren.com/tag/there-is-already-an-object-named-sqlogrendatcom-in-the-database/
- http://www.dailymotion.com/video/xc9inb_stored-procedure-sakli-yordam-kulla_tech

