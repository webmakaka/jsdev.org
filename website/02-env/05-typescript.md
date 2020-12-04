---
layout: page
title: Typescipt environment for development
description: Prepare environment for development typescript applications
keywords: typescript, ts, environment, development
permalink: /env/typescipt/
---

# Typescipt environment for development

<br/>

**Based on video course [FrontendMasters] Production-Grade TypeScript**

<br/>

https://github.com/mike-north/professional-ts

<br/>

**Configured project:**  
https://github.com/mike-north/professional-ts-my-lib

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

<!-- ```json
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
``` -->

```js
{
  "compilerOptions": {
    "composite": true,
    "strict": true,
    "module": "commonjs",
    "target": "es2018",
    "outDir": "dist",
    "rootDir": "src",
    "declaration": true,
    "sourceMap": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true,
    "stripInternal": true,
    "types": [],
    //"esModuleInterop": true,
    //"skipLibCheck": true
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

<br/>

    $ npm install --save-dev \
        eslint@latest \
        @typescript-eslint/parser@latest \
        @typescript-eslint/eslint-plugin@latest

<br/>

    // Generate config if needed
    // $ ./node_modules/.bin/eslint --init

<br/>

<br/>

**.eslintrc.json**

    $ vi .eslintrc.json

<br/>

```js
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:@typescript-eslint/recommended-requiring-type-checking"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": 12,
        "project": "tsconfig.eslint.json"
    },
    "plugins": [
        "@typescript-eslint"
    ],
    "rules": {
        "prefer-const": "error",
        "@typescript-eslint/no-unused-vars": "off",
        "@typescript-eslint/no-unused-params": "off"
    },
    "overrides": [{
        "files" : ["tests/**/*.ts"],
        "env": {"jest": true, "node": true}
    }]
}


```

<!-- ```js
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
``` -->

<br/>

**tsconfig.eslint.json**

```
{
    "extends": "./tsconfig.json",
    "compilerOptions": {
        "types": ["jest"]
    },
    "include": ["src", "tests"]
}

```

<br/>

**package.json**

```
  "lint": "eslint src server tests --ext .js,.ts,.jsx,.tsx",
```

<br/>

    $ npm lint

<br/>

### Jest

    $ npm install --save-dev jest @types/jest \
        @babel/preset-env @babel/preset-typescript

<br/>

    $ mkdir tests

<br/>

    $ vi tests/intex.test.ts

<br/>

    $ vi tests/tsconfig.json

```js
{
    "extends": "../tsconfig.json",
    "references": [{
        "name": "my-lib",
        "path": ".."
    }],
    "compilerOptions": {
        "types": ["test"],
        "rootDir": "..",
        "noEmit": true
    },
    "include" : ["."]
}

```

<br/>

**.babelrc**

```js
{
    "presets": [
        ["@babel/preset-env", {"targets": {"node": 10}}],
        "@babel/preset-typescript"
    ]
}
```

<br/>

### Webpack & TypeScript Setup

https://www.youtube.com/watch?v=sOUhEJeJ-kI
