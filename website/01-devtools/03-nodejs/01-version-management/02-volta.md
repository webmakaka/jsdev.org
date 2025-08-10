---
layout: page
title: Node Version Management (Volta) installation in Ubuntu 22.04
description: Node Version Management installation and usage
keywords: setup, node.js, volta, Node Version Management, Volta, install
permalink: /devtools/nodejs/version-management/volta/
---

# Node Version Management


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

### Remove volta


<br/>

```
// remove here
$ vi ~/.profile
```

<br/>


```
$ rm -rf ~/.volta/
```

