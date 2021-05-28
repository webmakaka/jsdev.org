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
    $ npm install --save-dev typescript ts-node

<br/>

<!--

    @microsoft/api-documenter \
    @microsoft/api-extractor \



```
$ npm install --save-dev \
    @babel/preset-env \
    @babel/preset-typescript \
    @types/jest \
    @typescript-eslint/eslint-plugin \
    @typescript-eslint/parser \
    eslint \
    jest
```

-->

<br/>

**tsconfig.json**

<br/>

    // You can generate default tsconfig.json
    // $ ./node_modules/.bin/tsc --init

<br/>

    $ vi tsconfig.json

```js
{
  "compilerOptions": {
    "target": "esnext",
    "baseUrl": "./src",
    "rootDir": "./src",
    "outDir": "./build",
    "strict": true,
    "rootDir": "./src",
    "outDir": "dist",
    "composite": true,
    "module": "commonjs",
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitAny": true,
    "noImplicitReturns": true,
    "stripInternal": true,
    "types": [],
    "forceConsistentCasingInFileNames": true
  },
  "include": ["src"]
}
```

<br/>

**Compiler Options**  
https://www.typescriptlang.org/docs/handbook/compiler-options.html

<br/>

    $ vi package.json

<br/>

**package.json**

```
***
"scripts": {
    "build": "NODE_PATH=./src tsc",
    "ts-node": "ts-node ./src/index.ts",
    "lint": "eslint src --ext js,ts,jsx,tsx",
    "test": "jest"
  },
***
```

<br/>

<a href="/env/eslint/typescript/">Eslint</a>
<a href="/env/jest/">Jest for TypeScript</a>

<br/>

### Webpack & TypeScript Setup

https://www.youtube.com/watch?v=sOUhEJeJ-kI

<br/>

### Example

**Example from video course [FrontendMasters] Production-Grade TypeScript**

<br/>
Possible
https://github.com/mike-north/professional-ts

<br/>

**Configured project:**  
https://github.com/mike-north/professional-ts-my-lib
