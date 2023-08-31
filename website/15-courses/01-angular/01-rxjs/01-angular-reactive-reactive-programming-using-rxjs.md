---
layout: page
title: Declarative Reactive Programming using RxJS in Angular
description: Declarative Reactive Programming using RxJS in Angular
keywords: courses, js, angular, rxjs, youtube, Leela Web Dev
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

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic07.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/3

<br/>

### 06. Understand Change Detection Strategy onPush and Default

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/4

<br/>

### 07. Advantage of unsubscribing the http observable in ngOnDestroy

<br/>

```
$ ng g c pages/Home
```

<br/>

### 08. Get Posts using Declarative Programming in Angular with async & without subscribe for observable

<br/>

```
$ ng g c pages/DeclarativePosts
```

<br/>

### 09. Combine Categories & Posts Observables using CombineLatest & ForkJoin Operators

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/5

<br/>

### 10. Filter Posts by the user selected category and display in the UI

<br/>

### 11. Data Stream vs Action Stream. Difference between the two Observable Streams in Angular RxJS

<br/>

### 12. Create Action Stream using BehaviorSubject & filter posts with selected Category

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/6

<br/>

### 13. Create the Posts UI to share the Action Stream between the components in Angular RxJS

<br/>

```
$ ng g c pages/AltPosts
$ ng g c components/SinglePost
```

<br/>

### 14. Create Action Stream using Subject for getting Post Details between components

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic08.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/7

<br/>

### 15. Show Error Messages using the catchError Operator and assign to the error Subject

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic09.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/8

<br/>

### 16. Caching the Observables http data using Share and shareReplay Operators

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic10.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/9

<br/>

### 17. Add Loading Spinner Component with Declarative Reactive Programming & Subject

<br/>

```
$ ng g c components/loading
```

<br/>

https://loading.io/css/

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic11.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/10

<br/>

### 18. How to Avoid multiple async for observables in template to increase performance

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/11

<br/>

### 18. How to Avoid multiple async for observables in template to increase performance

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/11

<br/>

### 19. Create Add Post button and Add Post UI in the Posts UI

<br/>

```
$ ng g c components/AddPost
```

<br/>

### 20. Design Add Post Form using Reactive Forms Module

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic12.png 'Angular NgRx'){: .center-image }

<br/>

### 21. Add the Post Details submitted using Merge and scan operator

<br/>

### 22. Send Post Request to save Post Details in the database using concatMap operator

<br/>

### 23. Completing Add Post Feature and fixing small issues while adding Post

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic13.png 'Angular NgRx'){: .center-image }

<br/>

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/12

<br/>

### 24. Create Edit Post Form Component for updating the existing Post Details

<br/>

```
$ ng g c components/UpdatePost
```

<br/>

### 25. Populate the Post Details in the update post form using Reactive Forms Module

<br/>

![Angular NgRx](/img/courses/angular/rxjs/angular-reactive-reactive-programming-using-rxjs/pic14.png 'Angular NgRx'){: .center-image }
