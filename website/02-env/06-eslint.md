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

**Based on video course [FrontendMasters] Production-Grade TypeScript**

<br/>

**Configured project :**  
https://github.com/mike-north/professional-ts-my-lib

<br/>

### ESlint for TypeScript

<br/>

```
$ npm install --save-dev \

    @typescript-eslint/eslint-plugin \
    @typescript-eslint/parser \
    eslint
```

<br/>

    // Generate eslint config if needed
    // $ ./node_modules/.bin/eslint --init

<br/>

<br/>

**.eslintrc.json**

    $ vi .eslintrc.json

<br/>

```json
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
  "plugins": ["@typescript-eslint"],
  "rules": {
    "prefer-const": "error",
    "@typscript-eslint/no-unused-vars": "off",
    "@typscript-eslint/no-unused-params": "off"
  },
  "overrides": [
    {
      "files": ["tests/**/*.ts"],
      "env": { "jest": true, "node": true }
    }
  ]
}
```

<br/>

no-unused-vars, no-unused-params - are specified in tsconfig already

<br/>

**tsconfig.eslint.json**

<br/>

```json
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
