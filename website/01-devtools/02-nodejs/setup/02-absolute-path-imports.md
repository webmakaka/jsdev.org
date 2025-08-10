---
layout: page
title: Absolute path imports for Node.js projects
description: Absolute path imports for Node.js projects
keywords: setup, node.js, Absolute path imports
permalink: /devtools/nodejs/setup/absolute-path-imports/
---

# Absolute path imports for Node.js projects

[Project Example](https://github.com/webmakaka/Test-Driven-Development-with-Nodejs)

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

**jsconfig.json**

<br/>

```js
{
  "compilerOptions": {
    "checkJs": true,
    "module": "esnext",
    "target": "esnext",
    "baseUrl": ".",
    "paths": {
      "~/*": ["src/*"]
    }
  },
  "exclude": ["node_modules", "**/node_modules/*"],
  "include": ["./src/**/*.js"]
}
```

<br/>

**package.json**

<br/>

Remove "type": "module" if it exists.

I did not find a good babel plugin for convert from common.js to esmodules.

<br/>

```js
"scripts": {
  "dev": "nodemon --exec babel-node --config-file ./babel.config.json src/index.js",
},
```

<br/>

**babel.config.json**

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

<br/>

### Additional webpack config for esModules

<br/>

**webpack.config.js**

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

To work in package.json should be present

```
"type": "module",
```
