---
layout: page
title: Absolute path imports for Node.js projects
description: Absolute path imports for Node.js projects
keywords: env, node.js, Absolute path imports
permalink: /env/nodejs/absolute-path-imports/
---

<br/>

# Absolute path imports for Node.js projects

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
