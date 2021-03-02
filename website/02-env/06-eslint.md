---
layout: page
title: Eslint
description: Eslint
keywords: eslint
permalink: /env/eslint/
---

<br/>

# Eslint

<br/>

### ESlint for TypeScript

<br/>

```
$ npm install --save-dev \
    eslint@latest \
    @typescript-eslint/parser@latest \
    @typescript-eslint/eslint-plugin@latest
```

<br/>

    // Generate config if needed
    // $ ./node_modules/.bin/eslint --init

<br/>

<br/>

**.eslintrc.json**

    $ vi .eslintrc.json

<br/>

```js
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:@typescript-eslint/recommended-requiring-type-checking"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": 12,
        "project": "tsconfig.eslint.json"
    },
    "plugins": [
        "@typescript-eslint"
    ],
    "rules": {
        "prefer-const": "error",
        "@typescript-eslint/no-unused-vars": "off",
        "@typescript-eslint/no-unused-params": "off"
    },
    "overrides": [{
        "files" : ["tests/**/*.ts"],
        "env": {"jest": true, "node": true}
    }]
}
```

<!-- ```js
{
    "parser": "@typescript-eslint/parser",
    "parserOptions" : {
        "ecmaVersion" : 2015,
        "sourceType" : "module"
    },
    "extends" : ["plugin:@typescript-eslint/recommended"],
    "env" : {"node": true},
    "rules" : {
        "indent" : "off",
        "@typescript-eslint/indent" : "off"
    }
}
``` -->

<br/>

**tsconfig.eslint.json**

<br/>

```js
{
    "extends": "./tsconfig.json",
    "compilerOptions": {
        "types": ["jest"]
    },
    "include": ["src", "tests"]
}
```

<br/>

**.eslintignore**

<br/>

```
/node_modules/
```

<br/>

**package.json**

```
  "lint": "eslint src --ext .js,.ts,.jsx,.tsx",
```

<br/>

```
$ npm run lint
```
