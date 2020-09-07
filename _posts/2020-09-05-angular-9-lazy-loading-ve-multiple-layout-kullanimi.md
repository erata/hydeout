---
layout: post
published: true
excerpt_separator: <!--more-->
title: Angular 9 – Lazy Loading ve Multiple Layout Kullanimi
tags:
  - angular
  - angular-9
  - angular-routing
categories:
  - angular
---
Bir site yapiyoruz. Sitede **anasayfa** bilesenleri,**yönetim paneli** ve ek olarak **404** sayfasi var. Normalde **app-routing.mudule.ts** de component bazli bir routing yapisi kurgulayabiliriz. Fakat sadelik ve kullanim kolayligi acisindan lazy-loading seklinde yüklenen modüler bir yapi kurgulayacagiz. Anasayfa bilesenlerini **SiteModule** altinda toplayacagiz. Site yönetim ile ilgili bilesenleri ise **DashboardModule** de toplayacagiz. PageNotFound mesaji icin ise bir component kullanacagiz.

{% include image.html src="site-yapi.PNG" width="50%" description="Örnek site yapimiz bu sekildedir." %}

**app-routing.mudule.ts** dosya icerigimiz su sekildedir:

{% highlight typescript %}
import { NgModule } from '@angular/core';
import {Routes, RouterModule, PreloadAllModules} from '@angular/router';
import {PageNotFoundComponent} from "./page-not-found/page-not-found.component";
import {AuthGaurdService} from "./services/auth-guard.service";
import {LandingPageLayoutComponent} from "./shared/layout/guest/landing-page-layout/landing-page-layout.component";

const routes: Routes = [
  {
    path: '',
    loadChildren: () => import('./modules/site/site.module').then(m => m.SiteModule),
    data: { preload: true }
  },
  {
    path: 'dashboard',
    loadChildren: () => import(`./modules/dashboard/dashboard.module`).then(m => m.DashboardModule),
    canActivate:[AuthGaurdService],
    data: { preload: true }
  },
  {
    path: '',
    component: LandingPageLayoutComponent,
    children: [
      { path: '**', component: PageNotFoundComponent }
      ]
  }
];

@NgModule({
  imports: [RouterModule.forRoot(routes, { useHash: false, onSameUrlNavigation: 'reload', preloadingStrategy: PreloadAllModules})],
  exports: [ RouterModule ]
})
export class AppRoutingModule { }
{% endhighlight %}

Görüldügü üzere **app-routing.mudule.ts** dosyamiz **SiteModule** ve **DashboardModule** featured module kullanimi ile oldukca sade bir görünüme kavustu.
Simdi ilk olarak SiteModule routing mekanizmasini ele alalim. **site-routing.mudule.ts** asagidaki gibidir: 

{% highlight typescript %}
import { NgModule } from '@angular/core';

import { Routes, RouterModule } from '@angular/router';

import {SignupComponent} from "./signup/signup.component";
import {LoginComponent} from "./login/login.component";
import {PostsListComponent} from "./posts-list/posts-list.component";
import {PostDetailsComponent} from "./post-details/post-details.component";
import {DefaultLayoutComponent} from "../../shared/layout/guest/default-layout/default-layout.component";
import {LandingPageLayoutComponent} from "../../shared/layout/guest/landing-page-layout/landing-page-layout.component";


const routes: Routes = [
  {
    path: '',
    component: DefaultLayoutComponent,
    children: [
      { path: '', redirectTo: 'posts', pathMatch: 'full' },
      { path: 'posts', component: PostsListComponent },
      { path: 'post/:id', component: PostDetailsComponent },
    ]
  },
  {
    path: '',
    component: LandingPageLayoutComponent,
    children: [
      { path: 'login', component: LoginComponent },
      { path: 'signup', component: SignupComponent }
    ]
  },

];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class SiteRoutingModule { }
{% endhighlight %}

Anasayfa icin kullandigimiz SiteModule component’leri iki ayri sablon kullaniyor: **DefaultLayoutComponent** ve **LandingPageLayoutComponent**. Simdi bu layoutlari ve layoutlara özgü ciktimizi ele alalim.
**default-layout.component.html** dosyamiz ve kullanim sonucu olusan ekran görüntüsü asagidaki gibidir:

{% highlight html %}
<site-navbar></site-navbar>
<div class="container mb-5">
  <div class="row">
    <div class="col-md-8">   
      <router-outlet></router-outlet>      
    </div>
    <div class="col-md-4">
      <site-sidebar></site-sidebar>
    </div>
  </div>
</div>
<site-footer></site-footer>
{% endhighlight %}

{% include image.html src="site-anasayfa.PNG" description="default-layout kullanimi sonucu olusan ciktimiz bu sekildedir." %}

**landing-page-layout.component.html** dosyamiz ve kullanim sonucu olusan ekran görüntüsü asagidaki gibidir:

{% highlight html %}
<site-navbar></site-navbar>
<div class="container">
  <div class="row">
    <div class="col-xs-12 col-12 my-3">
      <router-outlet></router-outlet>
    </div>
  </div>
</div>
{% endhighlight %}

{% include image.html src="site-anasayfa-signup.PNG" description="landing-page-layout kullanimi sonucu olusan ciktimiz bu sekildedir." %}

Ikinci olarak **DashboardModule** routing mekanizmasini ele alalim. **dashboard-routing.mudule.ts** asagidaki gibidir:

{% highlight typescript %}
import { NgModule } from '@angular/core';

import { Routes, RouterModule } from '@angular/router';
import {AddPostComponent} from "./add-post/add-post.component";
import {EditPostComponent} from "./edit-post/edit-post.component";
import {ListComponent} from "./list/list.component";
import {EditUserComponent} from "./edit-user/edit-user.component";
import {AuthorisedDefaultLayoutComponent} from "../../shared/layout/authorised/authorised-default-layout/authorised-default-layout.component";
import {AuthorisedLandingPageLayoutComponent} from "../../shared/layout/authorised/authorised-landing-page-layout/authorised-landing-page-layout.component";

const routes: Routes = [
  {
    path: '',
    component: AuthorisedDefaultLayoutComponent,
    children: [
      { path: '',  component: ListComponent },
      { path: 'user/edit', component: EditUserComponent },
    ]
  },
  {
    path: '',
    component: AuthorisedLandingPageLayoutComponent,
    children: [
      { path: 'post/add', component: AddPostComponent },
      { path: 'post/edit/:id', component: EditPostComponent },

    ]
  },
];

@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
export class DashboardRoutingModule { }
{% endhighlight %}

Yönetim paneli icin kullandigimiz **DashboardModule** component’leri iki ayri sablon kullaniyor: **AuthorisedDefaultLayoutComponent** ve **AuthorisedLandingPageLayoutComponent**. Simdi bu layoutlari ve layoutlara özgü ciktimizi ele alalim.
**authorised-default-layout.component.html** dosyamiz ve kullanim sonucu olusan ekran görüntüsü asagidaki gibidir:

{% highlight html %}
<app-authorised-navbar></app-authorised-navbar>
<div class="container">
  <div class="row">
    <div class="col-md-3">
      <app-authorised-sidebar></app-authorised-sidebar>
    </div>
    <div class="col-md-9 my-3">
      <router-outlet></router-outlet>
    </div>
  </div>
</div>
{% endhighlight %}

{% include image.html src="site-dashboard.PNG" description="authorised-default-layout kullanimi sonucu olusan ciktimiz bu sekildedir." %}

**authorised-landing-page-layout.component.html** dosyamiz ve kullanim sonucu olusan ekran görüntüsü asagidaki gibidir:

{% highlight html %}
<app-authorised-navbar></app-authorised-navbar>
<div class="container">
  <div class="row">
    <div class="col-xs-12 col-12 my-3">
      <router-outlet></router-outlet>
    </div>
  </div>
</div>
{% endhighlight %}

{% include image.html src="site-dashboard-add.PNG" description="authorised-landing-page-layout kullanimi sonucu olusan ciktimiz bu sekildedir." %}

Ücüncü olarak URL hatasi (PageNotFound durumu) icin app-routing.module.ts dosyamizda layout olarak landing-page-layout.component.html dosyasini kullandik. Örnek görüntü asagidaki gibidir:

{% include image.html src="site-page-not-found.PNG" description="Sayfa bulunamadi ekrani." %}

Görüldügü üzere Angular routing mekanizmasinda lazy-loading modül kullanimi ile routing mekanizmasi alt modüllere yayilarak daha sade ve yönetilebilir uygulamalar yapmak mümkün. Ayrica lazy-load modüllerde güvenlik ayari yapmak da oldukca kolay. Örnegin asagidakiki kod parcasinda DashboardModule icin AuthGaurdService güvenlik kontrolünü tek satirda ( canActivate:[AuthGaurdService])ekledik. Böylece “/dashboard/..” ile devam eden tüm sayfalar kullanicinin sisteme giris yapmasina tabi olarak calisacak.

{% highlight typscript %}
{
    path: 'dashboard',
    loadChildren: () => import(`./modules/dashboard/dashboard.module`).then(m => m.DashboardModule),
    canActivate:[AuthGaurdService],
    data: { preload: true }
  },
{% endhighlight %}

Umarim yararli olmustur.
