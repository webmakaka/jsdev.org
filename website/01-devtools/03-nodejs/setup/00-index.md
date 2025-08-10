---
layout: page
title: Node.js
description: Node.js
keywords: setup, node.js
permalink: /devtools/nodejs/setup/
---

# Node.js

### [Node version Management](/devtools/nodejs/version-management/nvm/)

### [Absolute path imports for Node.js projects](/devtools/nodejs/setup/absolute-path-imports/)

### [Jest with absolute path imports for Node.js projects](/devtools/nodejs/setup/jest/)

<br/>

### Global node_modules path

```
// show global packages location
$ npm root -g
```

<br/>

### Check updates for node packages

```
$ npm install -g npm-check-updates
$ ncu -u
$ npm install
```

<br/>

### Possible additional strong config

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


