---
layout: page
title: Node Version Management (NVM) installation in Ubuntu 20.04
description: Node Version Management installation and usage
keywords: node.js, volta, Node Version Management, nvm, install
permalink: /env/nodejs/nvm/
---

# Node Version Management

<br/>

## [Variatn 1]: Volta (Node Version Manager)

( Mike North - Tech Head Guy from LinkedIn recommend it)

<br/>

    $ curl https://get.volta.sh | bash

open new terminal window || logout / login

    // Volta will choose the latest LTS
    $ volta install node yarn

    // $ volta install node@12

    $ node --version
    v14.17.3

<br/>

    // Add current in package.json infor about node and yarn
    $ volta pin node yarn

<br/>

**package.json**

```
  "volta": {
    "node": "14.15.1",
    "npm": "6.14.9"
  },
```

<br/>

## [Variatn 2]: Node Version Manager (NVM) installation in Ubuntu 20.04

<br/>

### Install latest Node Version Manager (NVM)

    -- current version
    https://github.com/creationix/nvm/releases

<br/>

    -- installation

    $ LATEST_VERSION=$(curl --silent "https://api.github.com/repos/nvm-sh/nvm/releases/latest" | grep '"tag_name"' | sed -E 's/.*"([^"]+)".*/\1/')

    $ curl -o- https://raw.githubusercontent.com/creationix/nvm/${LATEST_VERSION}/install.sh | bash

<br/>

    $ export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

<br/>

    $ nvm --version
    0.36.0

<br/>

### Install latest Node.js LTS

    // install latest LTS
    $ nvm install --lts

    $ node --version
    v12.19.0

or

    -- show possible
    $ nvm ls-remote

    // (Latest LTS: Erbium)
    $ nvm install v12.19.0

    $ nvm use v12.19.0

    -- set default
    $ nvm alias default v12.19.0

    $ node --version
    v12.19.0

<br/>

### For fast switching

    $ {
      nvm install v12.19.0
      nvm use v12.19.0
      nvm alias default v12.19.0
    }

<br/>

    $ {
      nvm install v8.17.0
      nvm use v8.17.0
      nvm alias default v8.17.0
    }

<br/>

### Install latest NPM

    $ nvm install-latest-npm

    $ npm --version
    6.14.8

<br/>

### Possible additional configs

<br/>

**packages.json**

```json
"engines": {
    "node": ">=12.13.1",
    "npm": ">=6.13.4"
  },
```

<br/>

**.npmrc**

```
engine-strict=true
```

<br/>

### Check updates for node packages

    $ npm install -g npm-check-updates
    $ ncu -u
    $ npm install

<br/>

### Absolute path imports for Node.js projects

<br/>

**jsconfig.json**

<br/>

```js
{
  "compilerOptions": {
    "checkJs": true,
    "module": "commonjs",
    "target": "esnext",
    "baseUrl": "./src"
  },
  "exclude": ["node_modules", "**/node_modules/*"]
}
```

<br/>

**package.json**

<br/>

```js
"type": "module",
```

<br/>

```js
"scripts": {
  "start": "NODE_PATH=./src nodemon ./src/index.js"
},
```

<!--

<br/>

**.babelrc.js (I am not sure that this file is needed!)**

<br/>

```js
const path = require('path');
const jsConfig = require('./jsconfig.json');

module.exports = {
  presets: ['@babel/preset-env'],
  plugins: [
    [
      'module-resolver',
      {
        root: [path.resolve(jsConfig.compilerOptions.baseUrl)],
      },
    ],
  ],
};
```

<br/>

```
$ npm install --save-dev \
    @babel/core \
    @babel/node \
    @babel/cli \
    @babel/preset-env \
    babel-plugin-module-resolver \
    nodemon
```

**package.json**

<br/>

```js
  "scripts": {
    "start": "NODE_PATH=./src nodemon --exec babel-node ./src/index.js"
  },
```

-->

<br/>

**Helped me:**

https://dev.to/thatanjan/set-up-nodejs-project-with-babel-198p

https://medium.com/weekly-webtips/say-good-bye-relative-imports-in-nodejs-projects-65513bcdae6c
