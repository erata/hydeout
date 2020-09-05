---
layout: post
published: true
excerpt_separator: <!--more-->
title: Angular 9 – Multiple Layout Kullanimi
categories:
  - Angular
tags:
  - angular
  - Angular 9
  - Angular routing
---
Bir site yapiyoruz. Sitede anasayfa bilesenleri, yönetim paneli ve ek olarak 404 sayfasi var. Normalde **app-routing.mudule.ts** de component bazli bir routing yapisi kurgulayabiliriz. Fakat sadelik ve kullanim kolayligi acisindan modüler bir yapi kurgulayacagiz. Anasayfa bilesenlerini **SiteModule** altinda toplayacagiz. Site yönetim ile ilgili bilesenleri ise **DashboardModule** de toplayacagiz. **PageNotFound** mesaji icin ise bir component kullanacagiz.

Örnek site yapimiz su sekilde:
![site-yapi.PNG]({{site.baseurl}}/assets/media/site-yapi.PNG)

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

Anasayfa icin iki sablon kullandik. 

**site-routing.mudule.ts**
{% highlight typescript %}
import { NgModule } from '@angular/core';

import { Routes, RouterModule } from '@angular/router';

import {SignupComponent} from "./signup/signup.component";
import {LoginComponent} from "./login/login.component";
import {PostsListComponent} from "./posts-list/posts-list.component";
import {PostDetailsComponent} from "./post-details/post-details.component";
import {DefaultLayoutComponent} from "../../shared/layout/guest/layout/default-layout.component";
import {LandingPageLayoutComponent} from "../../shared/layout/guest/core-layout/landing-page-layout.component";

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
{% endhighlight %}

![site-anasayfa.PNG]({{site.baseurl}}/assets/media/site-anasayfa.PNG)

![site-anasayfa-signup.PNG]({{site.baseurl}}/assets/media/site-anasayfa-signup.PNG)

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

![site-dashboard.PNG]({{site.baseurl}}/assets/media/site-dashboard.PNG)

![site-dashboard-add.PNG]({{site.baseurl}}/assets/media/site-dashboard-add.PNG)

URL hatasi (sayfa bulunamadi durumu) hem site hem de yönetim paneli icin gerekli bir durum olacagi icin app-routing.module.ts kapsaminda ele aldik.

![site-page-not-found.PNG]({{site.baseurl}}/assets/media/site-page-not-found.PNG)

Umarim yararli olmustur.
