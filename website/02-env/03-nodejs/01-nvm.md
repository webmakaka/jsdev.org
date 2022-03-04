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

    $ exec -l $SHELL

    // Volta will choose the latest LTS
    $ volta install node yarn npm

    // $ volta install node@12

    $ node --version
    v16.13.2

<br/>

    // Add current version info inside package.json
    $ volta pin node yarn npm

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
