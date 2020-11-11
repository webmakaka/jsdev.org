---
layout: page
title: Typescipt environment for development
description: Prepare environment for development typescript applications
keywords: typescript, ts, environment, development
permalink: /env/typescipt/
---

# Typescipt environment for development

<br/>

    $ mkdir -p ~/projects/dev/ts/my-new-ts-project && cd ~/projects/dev/ts/my-new-ts-project
    $ npm init -y

    $ npm install --save-dev typescript @types/node

    // It is possible to generate default tsconfig.json
    // $ ./node_modules/.bin/tsc --init

<br/>

**tsconfig.json**

<br/>

    $ vi tsconfig.json

```json
{
  "compilerOptions": {
    "lib": ["es2015"],
    "module": "commonjs",
    "outDir": "dist",
    "sourceMap": true,
    "strict": true,
    "target": "es2015"
  },
  "include": ["src"]
}
```

<br/>

**tsc CLI Options**  
https://www.typescriptlang.org/docs/handbook/compiler-options.html

<br/>

### TSLINT is dead, we will use ESLINT

https://medium.com/palantir/tslint-in-2019-1a144c2317a9

<!--

    $ npm install --save-dev tslint
    $ ./node_modules/.bin/tslint --init

**tslint.json**

-->

<br/>

### Run

    $ mkdir src

    $ vi src/index.ts

```
console.log('Hello TypeScript!')
```

    $ ./node_modules/.bin/tsc
    $ node ./dist/index.js

<br/>

### ts-node

    $ npm install --save-dev ts-node
    $ ./node_modules/.bin/ts-node ./src/index.ts

<br/>

### Run, Build

    $ vi package.json

<br/>

**package.json**

```
***
"ts-node": "ts-node ./src/index.ts",
"build": "tsc",
***
```

<br/>

    $ npm run ts-node

<!--
https://github.com/bcherny/programming-typescript-answers
-->

<!--



-->
<!--
<br/>

**tsconfig.json**

```
***
"rootDir": "./src",
"outDir": "./build"
***
```

-->

<br/>

### ESlint for typescript

    $ npm install --save-dev \
        eslint \
        @typescript-eslint/parser \
        @typescript-eslint/eslint-plugin

<br/>

**.eslintrc.json**

    $ vi .eslintrc.json

```js
{
    "parser": "@typescript-eslint/parser",
    "parserOptions" : {
        "ecmaVersion" : 2015,
        "sourceType" : "module"
    },
    "extends" : ["plugin:@typescript-eslint/recommended"],
    "env" : {"node": true},
    "rules" : {
        "indent" : "off",
        "@typescript-eslint/indent" : "off"
    }
}
```

<br/>

### Webpack & TypeScript Setup

https://www.youtube.com/watch?v=sOUhEJeJ-kI
