---
layout: page
title: Typescipt environment for development
description: Prepare environment for development typescript applications
keywords: typescript, ts, environment, development
permalink: /devtools/nodejs/setup/typescript/
---

# Typescipt environment for development

<br/>

```
$ mkdir -p ~/projects/dev/ts/my-new-ts-project && cd ~/projects/dev/ts/my-new-ts-project
```

<br/>

```
$ npm init -y
$ yarn add --dev typescript ts-node
$ yarn add --dev @types/node
```

<br/>

**tsconfig.json**

<br/>

```
// You can generate default tsconfig.json
// $ ./node_modules/.bin/tsc --init
```

<br/>

```
$ vi tsconfig.json
```

<br/>

```js
{
  "compilerOptions": {
    "strict": true,
    "noImplicitAny": true,
    "target": "esnext",
    "module": "commonjs",
    "baseUrl": "./src",
    "rootDir": "./src",
    "outDir": "./build",
    "allowJs": false,
    "moduleResolution": "node",
    "sourceMap": true,
    "noImplicitReturns": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "skipLibCheck": true,
    "removeComments": true,
    "esModuleInterop": true,
    "downlevelIteration": false,
    "noFallthroughCasesInSwitch": true,
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true,
    "noPropertyAccessFromIndexSignature": true,
    "noUncheckedIndexedAccess": true,
    "forceConsistentCasingInFileNames": true,
    "resolveJsonModule": true
  },
  "exclude": ["node_modules"],
  "include": ["./src/**/*.ts", "./test/**/*.ts"]
}
```

<br/>

Can be helpful if tests not needed.

```
"exclude": ["node_modules", "**/*.spec.ts"],
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
    "ts-node": "NODE_PATH=./src ts-node ./src/index.ts",
    "lint": "NODE_PATH=./src eslint src --ext js,ts,jsx,tsx",
    "test": "NODE_PATH=./src jest"
  },
***
```

<br/>

<a href="/devtools/nodejs/setup/typescript/nodemon/">Nodemon</a>
<a href="/devtools/nodejs/setup/typescript/eslint/">Eslint</a>
<a href="/devtools/nodejs/setup/typescript/jest/">Jest for TypeScript</a>
<a href="/devtools/nodejs/setup/typescript/webpack/">WebPack for TypeScript</a>

<br/>

### Example

**Example from video course [FrontendMasters] Production-Grade TypeScript**

<br/>

https://github.com/mike-north/professional-ts

<br/>

**Configured project:**  
https://github.com/mike-north/professional-ts-my-lib

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
