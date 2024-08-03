---
layout: page
title: Typescript and Nodemon
description: Typescript and Nodemon
keywords: env, nodejs, typescript, nodemon
permalink: /setup/nodejs/typescript/nodemon/
---

# Typescript and Nodemon

<br/>

```
$ yarn add --dev nodemon
```

<br/>

**nodemon.json**

<br/>

```json
{
  "ignore": ["node_modules"],
  "watch": ["./src/**/*.ts"],
  "exec": "npm run start",
  "ext": "ts"
}
```

<br/>

**package.json**

```json
"scripts": {
    "start": "NODE_PATH=./src ts-node src/index.ts",
    "build": "NODE_PATH=./src tsc",
    "start:prod": "npm run build && NODE_PATH=./src node build/index.js",
    "start:dev": "NODE_PATH=./src nodemon"
  }
```

<br/>

```
$ npm run dev
```
