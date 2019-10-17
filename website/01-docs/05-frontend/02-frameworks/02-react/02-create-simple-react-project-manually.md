---
layout: page
title: Create simple react project manually
permalink: /frontend/react/create-simple-react-project-manually/
---


# Create simple react project manually

    $ cd /project/
    $ npm init -y

    $ npm install --save react react-dom
    $ npm install --save-dev babel-core babel-loader babel-preset-es2015 babel-preset-react

    $ npm install --save-dev webpack webpack-dev-server

<br/>
    
### Babel config file

<br/>

    # echo '{ "presets": ["es2015", "react"] }' > .babelrc

<br/>

<br/>
    
    $ mkdir -p public
    $ mkdir -p src

<br/>

    $ vi public/index.html

<br/>

{% highlight html linenos %}

<html>
    <head>
        <title></title>
    </head>

    <body>

        <div id="root"></div>

        <script src="bundle.js"></script>

    </body>

</html>
    
{% endhighlight %}

<br/>

    $ vi src/App.jsx

<br/>

{% highlight javascript linenos %}

import React from 'react';
import ReactDOM from 'react-dom';

function App(){
return (

<div>
<h1>React</h1>
</div>
);
}

ReactDOM.render(<App />, document.getElementById('root'));

{% endhighlight %}

<br/>

    $ vi webpack.config.js

<br/>

{% highlight javascript linenos %}

var webpack = require('webpack');
const path = require('path');

module.exports = {

    entry: './src/App.jsx',
    output: {
        path: path.resolve(__dirname, 'public'),
        filename: 'bundle.js'
    },

    module: {
        loaders: [
            {
                test: /\.jsx?$/,
                exclude: /node_modules/,
                loader: 'babel-loader'
            }
        ]
    },

    devtool: 'eval-source-map',

    resolve: {
        EXTENSIONS: ['', '.js', '.jsx']
    }

};

{% endhighlight %}

<br/>

    $ vi package.json

<br/>

{% highlight javascript linenos %}

"scripts": {
"start": "webpack-dev-server --host 0.0.0.0 --port 8080 --inline --content-base ./public"
},

{% endhighlight %}

<br/>

    $ npm run start

    http://localhost/
