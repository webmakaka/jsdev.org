---
layout: page
title: Node.js
description: Node.js
keywords: node.js
permalink: /env/nodejs/
---

# Node.js

### [Node version Management](/env/nodejs/versions/)

### [Jest](/env/nodejs/jest/)

<br/>

### Check updates for node packages

    $ npm install -g npm-check-updates
    $ ncu -u
    $ npm install

<br/>

### Absolute path imports for Node.js projects

<br/>

**jsconfig.json**

<br/>

```js
{
  "compilerOptions": {
    "checkJs": true,
    "module": "commonjs",
    "target": "esnext",
    "baseUrl": "./src"
  },
  "exclude": ["node_modules", "**/node_modules/*"]
}
```

<br/>

**package.json**

<br/>

```js
"type": "module",
```

<br/>

```js
"scripts": {
  "start": "NODE_PATH=./src nodemon ./src/index.js"
},
```

<br/>

### Possible additional configs

<br/>

**packages.json**

```json
"engines": {
    "node": ">=12.13.1",
    "npm": ">=6.13.4"
  },
```

<br/>

**.npmrc**

```
engine-strict=true
```
