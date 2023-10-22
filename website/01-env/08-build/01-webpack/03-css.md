---
layout: page
title: WebPack - CSS
description: WebPack - CSS
keywords: WebPack - CSS
permalink: /env/build/webpack/css/
---

# WebPack - CSS

<br/>

<div align="center">
    <img src="/img/env/build/webpack/css-01.png" alt="css webpack">
</div>

<br/>

<div align="center">
    <img src="/img/env/build/webpack/css-02.png" alt="css webpack">
</div>

<br/>

<br/>

    # npm install --save-dev css-loader style-loader

<br/>

    # npm install --save-dev extract-text-webpack-plugin@2

<br/>

    # vi webpack.config.js

<br/>

    const path = require('path');
    const ExtractTextPlugin = require('extract-text-webpack-plugin');

    const config = {

        entry: './src/index.js',
        output: {
            path: path.resolve(__dirname, 'build'),
            filename: 'bundle.js'
        },

        module: {
            rules: [
                {
                    use: 'babel-loader',
                    test: /\.js$/
                }
                // ,
                // {
                //     use: ['style-loader', 'css-loader'],
                //     test: /\.css$/
                // }
                ,{
                    loader: ExtractTextPlugin.extract({
                        loader: 'css-loader'
                    }),
                    test: /\.css$/
                }
            ]
        },
        plugins: [
            new ExtractTextPlugin('style.css')
        ]

    };


    module.exports = config;

<br/>

    # vi src/index.js

<br/>

    <html>
        <head>
            <link rel="stylesheet" href="build/style.css" />
        </head>
        <body>
            <script src="build/bundle.js"></script>
        </body>
    </html>

<br/>

    # vi src/index.js

<br/>

    import sum from './sum';
    import './image_viewer';

    const total = sum(10, 5);

    console.log(total);

<br/>

    # vi src/image_viewer.js

<br/>

    import '../styles/image_viewer.css';

    const image = document.createElement('img');
    image.src = 'http://lorempixel.com/400/400';

    document.body.appendChild(image);

<br/>

    # vi styles/image_viewer.css

<br/>

    img {
        border: 10px solid black;
    }

<br/>

    # npm run build
