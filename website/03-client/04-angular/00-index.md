---
layout: page
title: Angular
description: Angular
keywords: Angular
permalink: /client/angular/
---

# Angular

<br/>

### Angular cli

<!-- <br/>

```
$ volta install node@18 npm@9 yarn@3
``` -->

<br/>

```
$ node -v
v20.15.0
```

<br/>

```
$ npm -v
10.8.1
```

<!-- <br/>

```
$ yarn -v
3.5.1
```

<br/>

```
$ volta install @angular/cli
``` -->

<br/>

```
$ npm install -g @angular/cli
```

<br/>

```
$ ng version

     _                      _                 ____ _     ___
    / \   _ __   __ _ _   _| | __ _ _ __     / ___| |   |_ _|
   / △ \ | '_ \ / _` | | | | |/ _` | '__|   | |   | |    | |
  / ___ \| | | | (_| | |_| | | (_| | |      | |___| |___ | |
 /_/   \_\_| |_|\__, |\__,_|_|\__,_|_|       \____|_____|___|
                |___/

Angular CLI: 18.0.7
Node: 20.15.0
Package Manager: npm 10.8.1
OS: linux x64

Angular:
...

Package                      Version
------------------------------------------------------
@angular-devkit/architect    0.1800.7 (cli-only)
@angular-devkit/core         18.0.7 (cli-only)
@angular-devkit/schematics   18.0.7 (cli-only)
@schematics/angular          18.0.7 (cli-only)
```

<br/>

```
$ ng new angular-hello-world
$ cd angular-hello-world
$ ng serve --host 0.0.0.0 --port 8080
```

<br/>

**.prettierrc**

```
{
  "tabWidth": 2,
  "printWidth": 80,
  "semi": true,
  "singleQuote": true,
  "bracketSpacing": true
}

```

<br/>

**.prettierignore**

```
node_modules
# *.test.js
# *.spec.js
```

<br/>

**tsconfig.json**

```
    "strictPropertyInitialization": false,
    "noImplicitAny": false,
    "noImplicitReturns": false,
```

<br/>

**angular.json**

```
  "projects": {
    "app": {
      "projectType": "application",
      "schematics": {
        "@schematics/angular:component": {
          "skipTests": true
        }
      },
***
```

<br/>

**.gitignore**

```
*.~
*.*~
*.log
*.swp

node_modules/
logs/

.vscode
.angular/

.pnp.cjs
.pnp.loader.mjs

.yarn
```

<br/>

**Sample:**

https://github.com/wildmakaka/Angular-Declarative-Reactive-Programming-using-RxJS/pull/1/files

<br/>

### [Airbnb eslint for Angular](/client/angular/airbnb/)

<br/>

**Libs:**  
[Primeng](//primeng.org)
[Primeflex](//primefaces.org/primeflex/)

<br/>

## [Angular courses](/courses/frontend/angular/)

<br/>

## Angular code examples

### [RxJs](/courses/frontend/angular/rxjs/)

### [NgRx](/courses/frontend/angular/ngrx/)

### [[frontendmasters.com] Production-Grade Angular [2021, ENG]](https://github.com/onehungrymind/fem-production-angular)

### [Pockemons](https://github.com/nvkuznetsova/pokemons-fast-start-demo/tree/main)
