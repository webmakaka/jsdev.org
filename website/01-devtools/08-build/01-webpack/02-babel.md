---
layout: page
title: WebPack - Babel
description: WebPack - Babel
keywords: WebPack - Babel
permalink: /devtools/build/webpack/babel/
---

# WebPack - Babel

<br/>

<div align="center">
    <img src="/img/devtools/build/webpack/babel-01.png" alt="babel webpack">
</div>

<br/>
<br/>

<div align="center">
    <img src="/img/devtools/build/webpack/babel-02.png" alt="babel webpack">
</div>

<br/>

    $ yarn add -D webpack webpack-cli

<br/>

    $ yarn add -D babel-core babel-loader babel-preset-env

<br/>

    $ vi babel.config.json

<br/>

```
{
    "presets": ["babel-preset-env"]
}
```

<br/>

    $ vi webpack.config.js

<br/>

```js
const path = require('path');

const config = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'build'),
    filename: 'bundle.js',
  },
};

module.exports = config;
```

<br/>

**package.json**

<br/>

```
"webpack": "webpack"
```

<br/>

    $ yarn webpack

<br/>

[Config for node.js project](/devtools/nodejs/setup/absolute-path-imports/)
