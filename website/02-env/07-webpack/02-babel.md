---
layout: page
title: WebPack - Babel
description: WebPack - Babel
keywords: WebPack - Babel
permalink: /env/webpack/babel/
---

# WebPack - Babel

<br/>

<div align="center">
    <img src="/img/env/webpack/babel-01.png" alt="babel webpack">
</div>

<br/>
<br/>

<div align="center">
    <img src="/img/env/webpack/babel-01.png" alt="babel webpack">
</div>

<br/>

    # npm install --save-dev babel-core babel-loader babel-preset-env

<br/>

    # vi .babelrc

<br/>

    {
        "presets": ["babel-preset-env"]
    }

<br/>

    # vi webpack.config.js

<br/>

    const path = require('path');

    const config = {

        entry: './src/index.js',
        output: {
            path: path.resolve(__dirname, 'build'),
            filename: 'bundle.js'
        }

    };


    module.exports = config;

<br/>

    # npm run build
