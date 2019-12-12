---
layout: page
title: WebPack - Basics
permalink: /tasks-runner/webpack/basics/
---

<br/>


# WebPack - Basics


    # cd project
    # mkdir js_modules
    # cd js_modules
    # npm init -f

or

    # npm init -y

<br/>

    # npm install --save-dev webpack@2
    # touch webpack.config.js

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

    # vi package.json

    "scripts": {
      "build": "webpack"
    },


<br/>

    # vi src/index.js

<br/>

    const sum = require('./sum');

    const total = sum(10, 5);

    console.log(total);


<br/>

    # vi src/sum.js

<br/>

    const sum = (a, b) => a + b;

    module.exports = sum;

<br/>

    <html>
    <head>

    </head>
    <body>
        <script src="build/bundle.js"></script>
    </body>
    </html>


<br/>

    # npm run build
