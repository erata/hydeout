---
layout: post
published: true
excerpt_separator: <!--more-->
title: Angular 9 – Multiple Layout Kullanimi
tags:
  - angular
  - angular-9
  - angular-routing
categories:
  - angular
---
Bir site yapiyoruz. Sitede anasayfa bilesenleri, yönetim paneli ve ek olarak 404 sayfasi var. Normalde **app-routing.mudule.ts** de component bazli bir routing yapisi kurgulayabiliriz. Fakat sadelik ve kullanim kolayligi acisindan lazy-loading seklinde yüklenen modüler bir yapi kurgulayacagiz. Anasayfa bilesenlerini **SiteModule** altinda toplayacagiz. Site yönetim ile ilgili bilesenleri ise **DashboardModule** de toplayacagiz. PageNotFound mesaji icin ise bir component kullanacagiz.

[<img src="{{site.baseurl}}/assets/media/site-yapi.PNG" width="60%" title="Örnek site yapimiz bu sekildedir"/>]({{site.baseurl}}/assets/media/site-yapi.PNG)

**app-routing.mudule.ts**

{% highlight typescript %}
import { NgModule } from '@angular/core';
import {Routes, RouterModule, PreloadAllModules} from '@angular/router';
import {PageNotFoundComponent} from "./page-not-found/page-not-found.component";
import {AuthGaurdService} from "./services/auth-guard.service";
import {LandingPageLayoutComponent} from "./shared/layout/guest/core-layout/landing-page-layout.component";

 const routes: Routes = [
  {
    path: '',
    loadChildren: () = import('./modules/site/site.module').then(m = m.SiteModule),
    data: { preload: true }
  },
  {
    path: 'dashboard',
    loadChildren: () = import(`./modules/dashboard/dashboard.module`).then(m = m.DashboardModule),
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

Anasayfa (SiteModule) icin iki sablon kullandik: _DefaultLayoutComponent_ ve _LandingPageLayoutComponent_. 

**site-routing.mudule.ts**
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

Site anasayfamiz default-layout u kullanmakta ve görünümü asagidaki gibi:

**default-layout.component.html** dosyamiz su sekilde:
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

[<img src="{{site.baseurl}}/assets/media/site-anasayfa.PNG" width="60%"/>]({{site.baseurl}}/assets/media/site-anasayfa.PNG)

Sitede landing-page layoutunu kullanan signup component i ve ekran görünümü asagidaki gibi:

**landing-page.layout.html**
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

[<img src="{{site.baseurl}}/assets/media/site-anasayfa-signup.PNG" width="60%"/>]({{site.baseurl}}/assets/media/site-anasayfa-signup.PNG)

Yönetim panelinde de iki sablon kullandik. DashboardModule bilesenlerinin görünebilmesi icin sisteme giris yapmak gerekiyor (login).

**dashboard-routing.mudule.ts**

{% highlight typescript %}
import { NgModule } from '@angular/core';

import { Routes, RouterModule } from '@angular/router';
import {AddPostComponent} from "./add-post/add-post.component";
import {EditPostComponent} from "./edit-post/edit-post.component";
import {ListComponent} from "./list/list.component";
import {EditUserComponent} from "./edit-user/edit-user.component";
import {AuthorisedLayoutComponent} from "../../shared/layout/authorised/authorised-layout/authorised-layout.component";
import {AuthorisedCoreLayoutComponent} from "../../shared/layout/authorised/authorised-core-layout/authorised-core-layout.component";

const routes: Routes = [
  {
    path: '',
    component: AuthorisedLayoutComponent,
    children: [
      { path: '',  component: ListComponent },
      { path: 'user/edit', component: EditUserComponent },
    ]
  },
  {
    path: '',
    component: AuthorisedCoreLayoutComponent,
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

Site yönetim sayfasinin karsilama ekrani asagidaki gibi (authorised-default-layout):
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
[<img src="{{site.baseurl}}/assets/media/site-dashboard.PNG" width="60%"/>]({{site.baseurl}}/assets/media/site-dashboard.PNG)

Site yönetim panelinde authorised-landing-page-layout u kullanan yazi ekleme componenti asagidaki gibi:
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
[<img src="{{site.baseurl}}/assets/media/site-dashboard-add.PNG" width="60%"/>]({{site.baseurl}}/assets/media/site-dashboard-add.PNG)

URL hatasi (sayfa bulunamadi durumu) hem site hem de yönetim paneli icin gerekli bir durum olacagi icin app-routing.module.ts kapsaminda ele aldik.

sayfa bulunamadi görünümü asagidaki gibi:
[<img src="{{site.baseurl}}/assets/media/site-page-not-found.PNG" width="60%"/>]({{site.baseurl}}/assets/media/site-page-not-found.PNG)

Umarim yararli olmustur.
