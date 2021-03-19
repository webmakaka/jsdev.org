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

<br/>

```
$ npm install --save-dev \
    @babel/preset-env \
    @babel/preset-typescript \
    @microsoft/api-documenter \
    @microsoft/api-extractor \
    @types/jest \
    @typescript-eslint/eslint-plugin \
    @typescript-eslint/parser \
    eslint \
    jest \
    typescript
```

<br/>

    $ vi package.json

<br/>

**package.json**

```
***
"scripts": {
    "build": "tsc",
    "dev": "yarn build --watch --preserveWatchOutput",
    "lint": "eslint src --ext js,ts,jsx,tsx",
    "test": "jest"
  },
***
```

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
    "composite": true,
    "target": "ES2018",
    "module": "commonjs",
    "outDir": "dist",
    "rootDir": "src",
    "strict": true,
    "baseUrl": "./src",
    "noUnusedLocals": true,
    "noUnusedParameters": true ,
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

### ts-node useful for Node.js projects

    $ npm install --save-dev ts-node

<br/>

    $ vi package.json

<br/>

**package.json**

```
***
    "ts-node": "ts-node ./src/index.ts",
***
```

<br/>

```
$ npm run ts-node
```

<br/>

<a href="/env/eslint/typescript/">Eslint</a>
<a href="/env/jest/">Jest for TypeScript</a>

<br/>

### Webpack & TypeScript Setup

https://www.youtube.com/watch?v=sOUhEJeJ-kI
