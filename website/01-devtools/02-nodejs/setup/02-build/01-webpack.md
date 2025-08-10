---
layout: page
title: WebPack - Babel
description: WebPack - Babel
keywords: WebPack - Babel
permalink: /devtools/nodejs/setup/build/webpack/
---

# Nodejs - WebPack - Babel

<br/>

https://webpack.js.org/api/node/

<br/>

```
$ yarn add --dev webpack webpack-cli
```

<br/>

```
$ yarn add --dev babel-core @babel/core babel-loader babel-preset-env @babel/preset-env
```

<br/>

**package.json**

```
  "type": "module",

***

"webpack": "webpack"

```

<br/>

https://stackoverflow.com/questions/65300985/webpack-err-require-esm-must-use-import-to-load-es-module-but-i-am-using

https://stackoverflow.com/questions/59407534/can-i-use-as-es-modules-for-webpack-config

<br/>

```
$ yarn webpack
```

<br/>
<br/>
<br/>
<br/>
<br/>

```
$ yarn add --dev babel-plugin-module-resolver @babel/plugin-transform-runtime
```

<br/>
<br/>
<br/>
<br/>
<br/>

```
$ yarn add --dev webpack-node-externals
```

<br/>

```
$ vi webpack.config.js
```

<br/>

```js
import path from 'path';
import nodeExternals from 'webpack-node-externals';

const __dirname = path.dirname(new URL(import.meta.url).pathname);

export default {
  entry: path.resolve(__dirname, './src/index.js'),
  target: 'node',
  mode: 'development',
  externals: [nodeExternals()],
  module: {
    rules: [
      {
        test: /\.(js)$/,
        use: ['babel-loader'],
        resolve: {
          fullySpecified: false,
        },
      },
    ],
  },
  resolve: {
    extensions: ['*', '.js'],
  },
  output: {
    path: path.resolve(__dirname, './dist'),
    filename: 'bundle.js',
  },
  devServer: {
    contentBase: path.resolve(__dirname, './dist'),
  },
};
```

<br/>

**$ vi babel.config.json**

```js
{
  "presets": [
    [
      "@babel/preset-env",
      {
        "targets": {
          "esmodules": true,
          "node": true
        }
      }
    ]
  ],
  "plugins": [
    [
      "module-resolver",
      {
        "root": ["./src"],
        "alias": {
          "~": "./src"
        }
      }
    ]
  ]
}
```
