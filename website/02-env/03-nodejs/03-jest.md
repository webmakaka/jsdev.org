---
layout: page
title: Node Jest
description: Node Jest
keywords: node.js, jest
permalink: /env/nodejs/jest/
---

# Jest in nodejs project with absolute path

<br/>

```
$ yarn add -D jest supertest
```

<br/>

**package.json**

<br/>

```js
  "scripts": {
    "test": "NODE_PATH=./src jest --watchAll"
  },
```

<br/>

```
$ yarn add -D \
    @babel/core \
    @babel/node \
    @babel/cli \
    @babel/preset-env \
    babel-plugin-module-resolver \
    nodemon
```

<br/>

**babel.config.json**

<br/>

```json
{
  "presets": ["@babel/preset-env"],
  "plugins": [
    [
      "module-resolver",
      {
        "root": "./src"
      }
    ]
  ]
}
```

<!--

<br/>

**.babelrc.js**

<br/>

```js
const path = require('path');
const jsConfig = require('./jsconfig.json');

module.exports = {
  presets: ['@babel/preset-env'],
  plugins: [
    [
      'module-resolver',
      {
        root: [path.resolve(jsConfig.compilerOptions.baseUrl)],
      },
    ],
  ],
};
```

<br/>

```js
import * as path from 'path';
import jsConfig from './jsconfig.json';

export default {
  presets: ['@babel/preset-env'],
  plugins: [
    [
      'module-resolver',
      {
        root: [path.resolve(jsConfig.compilerOptions.baseUrl)],
      },
    ],
  ],
};
```

-->

<!--
$ yarn add -D @babel/plugin-transform-modules-commonjs
-->

<br/>

[Project Example](https://github.com/webmakaka/Test-Driven-Development-with-Nodejs)
