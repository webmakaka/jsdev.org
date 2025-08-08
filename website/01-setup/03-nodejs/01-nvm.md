---
layout: page
title: Node Version Management (NVM) installation in Ubuntu 22.04
description: Node Version Management installation and usage
keywords: setup, node.js, volta, Node Version Management, nvm, install
permalink: /setup/nodejs/nvm/
---

# Node Version Management

<br/>

## [Variatn 1]: Node Version Manager (NVM) installation in Ubuntu 22.04

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
CTRL^D, New Terminal
```

<br/>

```
$ nvm --version
0.40.3
```

<br/>

### Install latest Node.js LTS

```
// install latest LTS
$ nvm install --lts

$ nvm use --lts

$ node --version
v22.18.0
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
11.5.2
```

<br/>

### Yarn

```
$ npm install --global yarn
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
2.0.2
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
v22.18.0
```

<br/>

```
$ npm -v
11.5.2
```

<br/>

```
$ yarn -v
4.9.2
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
// example how to add your repo
$ vi .npmrc

registry=http://mylib.ru:8081/repository/npm-public-repo/
```

<br/>

```
// If yarn will not create node_modules folder create with next content
$ vi .yarnrc.yml
```

```
nodeLinker: node-modules
```
