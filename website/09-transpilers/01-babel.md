---
layout: page
title: Babel
permalink: /transpilers/babel/
---

<br/>


# Babel

    # npm init -y
    # npm install --save-dev babel-cli babel-core babel-preset-es2015


<br/>

    .babelrc

<br/>

    {
        "presets": [
            "latest"
        ]
    }


<br/>

package.json

<br/>

    "prestart": "babel-node my.js"
