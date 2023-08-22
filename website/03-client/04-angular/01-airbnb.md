---
layout: page
title: Airbnb eslint for Angular 16
description: Airbnb eslint for Angular 16
keywords: js, angular, lint, airbnb
permalink: /client/angular/airbnb/
---

# Airbnb eslint for Angular 16

**How to setup airbnb eslint for Angular 12**  
https://www.youtube.com/watch?v=G3d0ZoeA-mY

<br/>

```
$ ng lint
```

<br/>

```
$ npm info "eslint-config-airbnb-base@latest" peerDependencies
{ eslint: '^7.32.0 || ^8.2.0', 'eslint-plugin-import': '^2.25.2' }
```

<br/>

```
$ npm install --save-dev eslint-config-airbnb-base eslint-plugin-import eslint-config-airbnb-typescript
```

<br/>

```
$ vi angular.json
```

<br/>

```json
      "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:@angular-eslint/recommended",
        "plugin:@angular-eslint/template/process-inline-templates",
        "airbnb-base",
        "airbnb-typescript/base"
      ],
      "parserOptions": {
        "project": "./tsconfig.json"
      },
```

<br/>

```
$ ng lint --fix
```
