---
layout: page
title: Node Version Manager (NVM) installation on Ubuntu 18.04
permalink: /env/nodejs/
---

# Node Version Manager (NVM) installation on Ubuntu 18.04

<br/>

### Install packages

    -- for node.js installation
    # apt-get update && apt-get install -qq -y vim git curl net-tools
    # apt-get install -y node.js

<br/>

### Install latest Node Version Manager (NVM)

    -- current version
    https://github.com/creationix/nvm/releases

<br/>

    -- installation
    $ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.35.1/install.sh | bash

<br/>

    $ export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

<br/>

    $ nvm --version
    0.35.1

<br/>

### Install latest Node.js LTS

    // install latest LTS
    $ nvm install --lts

or

    -- show possible
    $ nvm ls-remote

    // (Latest LTS: Dubnium)
    $ nvm install v12.13.1

    $ nvm use v12.13.1

    -- set default
    $ nvm alias default v12.13.1

    $ node --version
    v12.13.1

<br/>

### Install latest NPM

    $ nvm install-latest-npm

    $ npm --version
    6.13.2


<br/>

### Possible additional configs


ECMAScript Modules In Node

https://www.youtube.com/watch?v=orp2Fnvzrgw


<br/>

$ npm install --save-dev \
    @babel/core \
    @babel/node \
    @babel/preset-env


<br/>

**.babelrc**

```
{
  "presets": ["@babel/preset-env"]
}

```



<br/>

**packages.json**

```
"engines": {
    "node": "12.13.1",
    "npm": "6.13.4"
  },

***

"start": "nodemon --exec babel-node server.js",

```

<!--



$ npm install -g babel-node

<br/>

$ npm install --save dev \
        babel-cli \
        babel-eslint \
        babel-loader \
        babel-preset-es2015 \
        babel-preset-stage-2 \
        eslint \
        babel-eslint






<br/>

**.eslintrc.js**

```
module.exports = {
  parser: 'babel-eslint',
  env: {
    browser: true,
    commonjs: true,
    es6: true,
    node: true
  },
  extends: ['eslint:recommended'],
  parserOptions: {
    ecmaFeatures: {
      experimentalObjectRestSpread: true,
      jsx: true
    },
    sourceType: 'module'
  },
  rules: {
    indent: ['error', 2],
    'linebreak-style': ['error', 'unix'],
    quotes: ['error', 'single'],
    semi: ['error', 'always'],
    'no-console': ['warn', { allow: ['info', 'error'] }]
  }
};
```




<!--

,
  "rules": {
    "no-extra-semi": "error",
    "semi": [2, "always"],
    "arrow-parens": [2, "always"]
  }
  
-->

<!--
    "jsx-a11y/label-has-for": 0,
-->


<!-- <br/>

**package.json**

```js
"lint": "./node_modules/.bin/eslint **/*.js",
"start": "npm run lint & nodemon server.js"
``` -->



<!--

<br/>

# Lint

```bash
$ npm install --save-dev eslint-config-react-app eslint-plugin-react
$ npm install --save-dev eslint-plugin-flowtype
$ npm install --save-dev babel-eslint
```


<br/>

    $ npm install --save-dev eslint eslint-config-prettier eslint-plugin-prettier


<br/>

# Babel

    $ npm install --save-dev babel-eslint babel-core babel-preset-env babel-plugin-transform-class-properties

<br/>

**.babelrc**

<br/>

```js
{
  "presets": [
    [
      "env",
      {
        "targets": {
          "browsers": ["last 2 versions"]
        }
      }
    ]
  ],
  "plugins": ["transform-class-properties"]
}
```

<br/>

**.eslintrc**

```js
{
  …
  "parser": "babel-eslint",
  …
}
```

<br/>

### JSHINT (Possible not needed)

**.jshintrc**

```js
{
  "predef": ["angular"]
}

"undef" : true, // Require all non-global variables be declared before they are used.
"strict" : true // Require `use strict` pragma in every file.

```
-->

<!--


<br/>

### Esling Standard

    $ npm install --save-dev eslint eslint-config-standard eslint-plugin-import eslint-plugin-node eslint-plugin-promise eslint-plugin-standard

<br/>

**.eslintrc**

<br/>

```js
{
  "extends": "standard",
  "rules": {
    "no-extra-semi": "error",
    "semi": [2, "always"]
  }
}
```

-->
