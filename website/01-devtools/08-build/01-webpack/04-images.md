---
layout: page
title: WebPack - Images
description: WebPack - Images
keywords: WebPack - Images
permalink: /devtools/build/webpack/images/
---

# WebPack - Images

<br/>

<div align="center">
    <img src="/img/devtools/build/webpack/images-01.png" alt="css webpack">
</div>

<br/><br/>

<div align="center">
    <img src="/img/devtools/build/webpack/images-02.png" alt="css webpack">
</div>

<br/>

    # npm install --save-dev image-webpack-loader url-loader

<br/>

    # npm install --save-dev file-loader

<br/>

lorempixel.com/1200/1200/

lorempixel.com/200/200/

<br/>

    # vi webpack.config.js

<br/>

    const path = require('path');
    const ExtractTextPlugin = require('extract-text-webpack-plugin');

    const config = {

        entry: './src/index.js',
        output: {
            path: path.resolve(__dirname, 'build'),
            filename: 'bundle.js',
            publicPath: 'build/'
        },

        module: {
            rules: [
                {
                    use: 'babel-loader',
                    test: /\.js$/
                },
                {
                    loader: ExtractTextPlugin.extract({
                        loader: 'css-loader'
                    }),
                    test: /\.css$/
                },
                {
                    test: /\.(jpe?g|png|gif|svg)$/,
                    use: [
                        {
                            loader: 'url-loader',
                            options: { limit: 40000 }
                        },
                        'image-webpack-loader'
                    ]
                }
            ]
        },
        plugins: [
            new ExtractTextPlugin('style.css')
        ]

    };


    module.exports = config;

<br/>

    # vi src/image_viewer.js

<br/>

    import big from '../assets/big.jpg';
    import small from '../assets/small.jpg';
    import '../styles/image_viewer.css';

    const image = document.createElement('img');
    image.src = small;

    document.body.appendChild(image);



    const bigImage = document.createElement('img');
    bigImage.src = big;

    document.body.appendChild(bigImage);

<br/>

    # npm run build
