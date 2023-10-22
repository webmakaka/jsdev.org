---
layout: page
title: WebPack for TypeScript - make bundle without babel
description: WebPack for TypeScript - make bundle without babel
keywords: env, WebPack for TypeScript - make bundle without babel
permalink: /env/nodejs/typescript/webpack/
---

<br/>

# WebPack for TypeScript - make bundle without babel

<br/>

```
$ yarn add --dev \
    webpack-cli
```

<br/>

**package.json**

```json
  "scripts": {
    "start": "NODE_PATH=./src ts-node src/index.ts",
    "build": "NODE_PATH=./src tsc",
    "start:prod": "npm run build && NODE_PATH=./src node build/index.js",
    "start:dev": "NODE_PATH=./src nodemon",
    "webpack:bundle": "webpack --mode production",
    "start:bundle": "npm run webpack:bundle && NODE_PATH=./src node dist/bundle.js"
  },
```

<br/>

**webpack.config.ts**

```ts
import dotenv from 'dotenv';
import path from 'path';
import { DefinePlugin } from 'webpack';

//const __dirname = path.dirname(new URL(import.meta.url).pathname);

export default {
  target: 'node',
  entry: './src/index.ts',
  devtool: 'inline-source-map',
  module: {
    rules: [
      {
        test: /\.ts?$/,
        use: 'ts-loader',
        exclude: /node_modules/,
      },
    ],
  },
  resolve: {
    extensions: ['.ts', '.js'],
  },
  output: {
    filename: 'bundle.js',
    // path: path.resolve(__dirname, 'dist'),
    path: path.resolve('.', 'dist'),
  },
  plugins: [
    new DefinePlugin({
      'process.env': `(${JSON.stringify(dotenv.config().parsed)})`,
    }),
  ],
};
```

<br/>

https://github.com/wildmakaka/rss-nodejs-2022-task3-crud-api

<br/>

### Example 2

<br/>

https://www.youtube.com/watch?v=ILEX6mKgB2E

<br/>

https://github.com/DanWahlin/Getting-Started-With-TypeScript/tree/main/Adding%20WebPack%20to%20a%20TypeScript%20Project
