---
layout: page
title: Declarative Reactive Programming using RxJS in Angular
description: Declarative Reactive Programming using RxJS in Angular
keywords: js, angular, rxjs, youtube
permalink: /courses/angular/rxjs/angular-declarative-reactive-programming-using-rxjs/
---

# [[YouTube] [Leela Web Dev] Declarative Reactive Programming using RxJS in Angular [ENG, 2021][6 hours, 23 minutes, 54 seconds]](https://www.youtube.com/playlist?list=PL_euSNU_eLberdNLX5idpheqHLjdZltJy)

<br/>

**original src**  
https://github.com/leelanarasimha/Angular-Declarative-Posts

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS

<br/>

### 01. Introduction to Declarative Reactive Programming vs Imperative Programming in Angular RxJS.

<br/>

### 02. Setup Angular Project and Firebase database step by step. Install RxJS Latest Version

```
> ng new app
? Would you like to add Angular routing? (y/N) y

? Which stylesheet format would you like to use? SCSS
```

<br/>

console.firebase.google.com

Realtime Database

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic01.png 'Angular NgRx'){: .center-image }

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic02.png 'Angular NgRx'){: .center-image }

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic03.png 'Angular NgRx'){: .center-image }

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic04.png 'Angular NgRx'){: .center-image }

<br/>

```json
{
  "rules": {
    ".read": "true",
    ".write": "true"
  }
}
```

<br/>

```
$ npm install rxjs@latest
$ npm install bootstrap@latest
```

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS

<br/>

### 03. Get Posts from firebase api using HttpClient. Call in component ngOnInit with Subscribe

<br/>

```
$ ng g c components/Header
$ ng g c pages/Posts
```

<br/>

https://getbootstrap.com/docs/5.3/components/navbar/#how-it-works

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic05.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/1/files

<br/>

### 04. Format Posts Response using RxJS Map Operator and display in the template using ngFor

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic06.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/2

<br/>

### 05. Get Categories using Higher Order Mapping Operators using mergeMap

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/3

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic07.png 'Angular NgRx'){: .center-image }
