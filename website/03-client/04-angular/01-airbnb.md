---
layout: page
title: Airbnb eslint for Angular 12
description: Airbnb eslint for Angular 12
keywords: js, angualr, lint, airbnb
permalink: /client/angular/airbnb/
---

# Airbnb eslint for Angular 12

**How to setup airbnb eslint for Angular 12**  
https://www.youtube.com/watch?v=G3d0ZoeA-mY

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
$ ng lint --fix
```
