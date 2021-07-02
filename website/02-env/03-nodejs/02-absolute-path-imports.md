---
layout: page
title: Absolute path imports for Node.js projects
description: Absolute path imports for Node.js projects
keywords: env, node.js, Absolute path imports
permalink: /env/nodejs/absolute-path-imports/
---

<br/>

# Jest with absolute path imports for Node.js projects

https://www.npmjs.com/package/babel-plugin-module-resolver

Something wrong and not working as i want. Looking for a solution. If you know how to fix, please download project example and make PR to fix.

[Project Example](https://github.com/webmakaka/Test-Driven-Development-with-Nodejs)

<br/>

[Node.js prepared as here](/env/nodejs/absolute-path-imports/)

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

### Need to Check

https://www.npmjs.com/package/babel-plugin-root-import

https://koprowski.it/import-alias-in-react-native-and-vscode/
