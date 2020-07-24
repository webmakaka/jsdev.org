---
layout: page
title: Typescipt environment for development
description: Prepare environment for development typescript applications
keywords: typescript, environment, development
permalink: /env/typescipt/
---

# Typescipt environment for development

    $ npm install --save-dev typescript ts-node

<!--
 ts-node-dev
-->

    $ npm install --save-dev @types/node @types/express

    // generate default tsconfig.json
    $ tsc --init

<br/>

**tsconfig.json**

```
***
"rootDir": "./src",
"outDir": "./build"
***
```

<br/>

    $ ts-node index.ts

<br/>

### Build

<br/>

**package.json**

```
***
"build": "tsc --project ./",
***
```

<br/>

### Eslint for typescript

    $ npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/elslint-plugin

<br/>

**.eslintrc.json**

```js
{
    "parser": "@typescript-eslint/parser",
    "parserOptions" : {
        "ecmaVersion" : 2018,
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

<!--

"@typescript-eslint/explicit-function-return-type" : "off"

-->

<br/>

**Visual Studio Themes:**

CTRL + P

> Preferences: Open Settings (JSON)

```
***
// eslint
"eslint.validate": [
    "javascript",
    "javascriptreact"
],
***
```

<br/>

### Webpack & TypeScript Setup

https://www.youtube.com/watch?v=sOUhEJeJ-kI
