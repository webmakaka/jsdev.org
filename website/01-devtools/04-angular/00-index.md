---
layout: page
title: Angular 18
description: Angular 18
keywords: setup, Angular 18
permalink: /devtools/angular/setup/
---

# Angular 18

<br/>

### Angular cli

<!-- <br/>

```
$ volta install node@18 npm@9 yarn@3
``` -->

<br/>

```
$ node -v
v22.18.0
```

<br/>

```
$ npm -v
11.5.2
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
// show available versions
$ npm view @angular/cli versions
```

```
// install latest
$ npm install -g @angular/cli@latest
$ npm cache clean --force
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

Angular CLI: 20.1.5
Node: 22.18.0
Package Manager: npm 11.5.2
OS: linux x64

Angular: 20.1.6
... common, compiler, compiler-cli, core, forms
... platform-browser, router

Package                      Version
------------------------------------------------------
@angular-devkit/architect    0.2001.5
@angular-devkit/core         20.1.5
@angular-devkit/schematics   20.1.5
@angular/build               20.1.5
@angular/cli                 20.1.5
@schematics/angular          20.1.5
rxjs                         7.8.2
typescript                   5.8.3
zone.js                      0.15.1
```

<br/>

```
$ ng new angular-hello-world
$ cd angular-hello-world
$ ng serve --host 0.0.0.0 --port 8080
```

<br/>

**.prettierrc**

```json
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

```json
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

**package.json**

```json
***
      "start": "ng serve --host 0.0.0.0 --port 8080",
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

### [Airbnb eslint for Angular](/devtools/angular/setup/airbnb/)

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




<br/>

### The Angular CLI requires a minimum Node.js version of


```
$ npm start

> techline.ru@0.0.0 start
> ng serve

Node.js version v22.5.1 detected.
The Angular CLI requires a minimum Node.js version of v20.19 or v22.12.

Please update your Node.js version or visit https://nodejs.org/ for additional instructions.
```

<br/>

```
$ node -v
v22.18.0
```


<br/>

```
$ npx node -v
v22.5.1
```

<br/>

```
$ which npx
/home/marley/.volta/bin/npx
```

<br/>

```
$ npx clear-npx-cache
```



npm install -g npm@latest --force