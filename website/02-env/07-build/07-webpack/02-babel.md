---
layout: page
title: WebPack - Babel
description: WebPack - Babel
keywords: WebPack - Babel
permalink: /env/build/webpack/babel/
---

# WebPack - Babel

<br/>

<div align="center">
    <img src="/img/env/build/webpack/babel-01.png" alt="babel webpack">
</div>

<br/>
<br/>

<div align="center">
    <img src="/img/env/build/webpack/babel-02.png" alt="babel webpack">
</div>

<br/>

    $ yarn add -D webpack@2
    $ yarn add -D webpack-cli

<br/>

    $ yarn add -D babel-core babel-loader babel-preset-env

<br/>

    $ vi .babelrc

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

<!-- <br/>

```js
const path import 'path';

export const config = {
    entry: './src/index.js',
    output: {
        path: path.resolve(__dirname, 'build'),
        filename: 'bundle.js'
    }
};
``` -->

<br/>

**package.json**

<br/>

```
"build:webpack":·"webpack"
```

<br/>

    $ yarn build:webpack
