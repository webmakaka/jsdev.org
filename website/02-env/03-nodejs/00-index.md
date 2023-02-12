---
layout: page
title: Node.js
description: Node.js
keywords: node.js
permalink: /env/nodejs/
---

# Node.js

### [Node version Management](/env/nodejs/nvm/)

### [Absolute path imports for Node.js projects](/env/nodejs/absolute-path-imports/)

### [Jest with absolute path imports for Node.js projects](/env/nodejs/jest/)

<br/>

### Global node_modules path

    $ npm root -g

<br/>

### Check updates for node packages

    $ npm install -g npm-check-updates
    $ ncu -u
    $ npm install

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
