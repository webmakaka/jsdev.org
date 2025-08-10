---
layout: page
title: Cypress
description: Cypress
keywords: js, testing, cypress
permalink: /tools/testing/cypress/
---

# Cypress

<br/>

### [YouTube][qavbox] Cypress typescript tutorial [ENG, 2021]

https://www.youtube.com/watch?v=j1YNpo8gG1c&list=PLPO0LFyCaSo1sEDJb6FR2a1iPl-48FDBL

<br/>

```
$ mkdir cypress
$ cd cypress

$ npm init -y
$ npm install cypress
$ npm install --save-dev typescript
```

<br/>

```
$ vi package.json
```

<br/>

```json
 “scripts”: {
    "cypress:open": "cypress open",
    "cypress:run": "cypress run"
  },
```

<br/>

https://docs.cypress.io/app/tooling/typescript-support#Configure-tsconfig-json

<br/>

```
$ vi tsconfig.json
```

<br/>

```json
{
  "compilerOptions": {
    "target": "es5",
    "lib": ["es5", "dom"],
    "sourceMap": true,
    "types": ["cypress", "node"]
  },
  "include": ["**/*.ts"]
}
```

<br/>

```
$ npm run cypress:open
```

<br/>

### [[YouTube] [SDET- QA Automation Techie] Cypress - JavaScript End to End Testing [ENG, 2022]](https://github.com/wildmakaka/Cypress-JavaScript-End-to-End-Testing)

<br/>

### cypress-realworld-app

https://github.com/cypress-io/cypress-realworld-app
