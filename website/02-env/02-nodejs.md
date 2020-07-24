---
layout: page
title: Node Version Manager (NVM) installation on Ubuntu 18.04
description: Node Version Manager installation and usage
keywords: node.js, Node Version Manager
permalink: /env/nodejs/
---

# Node Version Manager (NVM) installation on Ubuntu 18.04

<br/>

### Install packages

    -- for node.js installation
    # apt-get update && apt-get install -qq -y vim git curl net-tools
    $ sudo apt-get install -y node.js

<br/>

### Install latest Node Version Manager (NVM)

    -- current version
    https://github.com/creationix/nvm/releases

<br/>

    -- installation
    $ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.35.2/install.sh | bash

<br/>

    $ export NVM_DIR="$HOME/.nvm"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

<br/>

    $ nvm --version
    0.35.2

<br/>

### Install latest Node.js LTS

    // install latest LTS
    $ nvm install --lts

    $ node --version
    v12.16.1

or

    -- show possible
    $ nvm ls-remote

    // (Latest LTS: Erbium)
    $ nvm install v12.16.1

    $ nvm use v12.16.1

    -- set default
    $ nvm alias default v12.16.0

    $ node --version
    v12.16.0

<br/>

### Install latest NPM

    $ nvm install-latest-npm

    $ npm --version
    6.13.7

<br/>

### Possible additional configs

<br/>

**packages.json**

```
"engines": {
    "node": ">=12.13.1",
    "npm": ">=6.13.4"
  },

***
```

**.npmrc**

```
engine-strict=true
```
