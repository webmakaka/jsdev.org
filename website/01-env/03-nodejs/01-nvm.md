---
layout: page
title: Node Version Management (NVM) installation in Ubuntu 20.04
description: Node Version Management installation and usage
keywords: node.js, volta, Node Version Management, nvm, install
permalink: /env/nodejs/nvm/
---

# Node Version Management

<br/>

## [Variatn 1]: Node Version Manager (NVM) installation in Ubuntu 20.04

<br/>

### Install latest Node Version Manager (NVM)

```
// current version
https://github.com/creationix/nvm/releases
```

<br/>

```

// installation
$ LATEST_VERSION=$(curl --silent "https://api.github.com/repos/nvm-sh/nvm/releases/latest" | grep '"tag_name"' | sed -E 's/.*"([^"]+)".*/\1/')

$ echo $LATEST_VERSION

$ curl -o- https://raw.githubusercontent.com/creationix/nvm/${LATEST_VERSION}/install.sh | bash
```

<br/>

```
$ export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

<br/>

```
$ nvm --version
0.39.7
```

<br/>

### Install latest Node.js LTS

```
// install latest LTS
$ nvm install --lts

$ node --version
v20.15.0
```

or

```
-- show possible
$ nvm ls-remote

// (Latest LTS: Erbium)
$ nvm install v12.19.0

$ nvm use v12.19.0

-- set default
$ nvm alias default v12.19.0

$ node --version
v12.19.0
```

<br/>

### For fast switching

```
$ {
  nvm install v20.15.0
  nvm use v20.15.0
  nvm alias default v20.15.0
}
```

<br/>

```
$ {
  nvm install v8.17.0
  nvm use v8.17.0
  nvm alias default v8.17.0
}
```

<br/>

### Install latest NPM

```
$ nvm install-latest-npm

$ npm --version
10.8.1
```

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

## [Variatn 2]: Volta (Node Version Manager)

<br/>

```
$ curl https://get.volta.sh | bash

$ exec -l $SHELL
```

<br/>

```
$ volta --version
1.1.1
```

<br/>

<!--
pnpm
-->

```
// Volta will choose the latest LTS
$ volta install node yarn npm

// $ volta install node@18 npm@9 yarn@3
```

<br/>

```
$ node -v
v20.14.0
```

<br/>

```
$ npm -v
10.8.1
```

<br/>

```
$ yarn -v
4.3.0
```

<!--

```
$ pnpm -v
8.14.1
``` -->

<br/>

```
// Add current version info inside package.json
$ volta pin node yarn npm
```

<br/>

**package.json**

```
  "volta": {
    "node": "v18.14.0",
    "npm": "9.6.0"
  },
```

<br/>

```
// Disable asking for money
$ npm config set fund false --location=global
```

<br/>

```
// Specify registry
$ npm config set registry https://registry.npmjs.org/

$ npm get registry

$ npm config list
```

<br/>

```
$ vi .npmrc

registry=http://repolib-main.ru:8081/repository/npm-public-repo/
```

<br/>

```
// If yarn will not create node_modules folder create with next content
$ vi .yarnrc.yml
```

```
nodeLinker: node-modules
```
