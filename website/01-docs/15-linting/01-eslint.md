---
layout: page
title: Eslint
permalink: /linting/eslint/
---

<br/>

# Eslint

[React.js environment for development](/frontend/react/env/)

<br/>

### Standard

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

<br/>

### Node.js

https://github.com/mysticatea/eslint-plugin-node
