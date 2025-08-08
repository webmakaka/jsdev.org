---
layout: page
title: Node.js
description: Node.js
keywords: setup, node.js
permalink: /setup/nodejs/
---

# Node.js

### [Node version Management](/setup/nodejs/nvm/)

### [Absolute path imports for Node.js projects](/setup/nodejs/absolute-path-imports/)

### [Jest with absolute path imports for Node.js projects](/setup/nodejs/jest/)

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
