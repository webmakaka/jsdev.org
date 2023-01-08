---
layout: page
title: Prettier
description: Prettier
keywords: env, prettier, eslint
permalink: /env/prettier/
---

# Prettier

<br/>

```
$ yarn add -D eslint
$ yarn add -D prettier eslint-config-prettier eslint-plugin-prettier
```

<br/>

**.prettierrc**

```js
{
  "printWidth": 120,
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true,
  "bracketSpacing": true,
  "arrowParens": "always"
}
```

<br>

**"arrowParens": "always" If you need to always use brackets for function with single argument (x) **

<br/>

**.prettierignore**

```
node_modules
*.test.js
*.spec.js
```

<br/>

**package.json**

```json

  "eslintConfig": {
    "parserOptions": {
      "ecmaVersion": 6
    },
    "extends": [
      "eslint:recommented",
      "plugin:prettier/recommended"
    ],
    "plugins": [
      "prettier"
    ],
    "env": {
      "node": true,
      "es6": true,
      "jest": true
    },
    "rules": {
      "eqeqeq": "warn",
      "prettier/prettier": "warn"
    }
  }
```

<br/>

```json
"scripts": {
    "format": "prettier --write src/**/*.{js,html}",
    "format:check": "prettier --list-different src/**/*.{js,html}",
    "lint": "eslint . --fix"
  }
```
