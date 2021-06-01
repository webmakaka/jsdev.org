---
layout: page
title: ESlint for TypeScript
description: ESlint for TypeScript
keywords: env, eslint, typescipt, ESlint for TypeScript
permalink: /env/nodejs/typescript/eslint/
---

<br/>

# ESlint for TypeScript

<br/>

**Based on video course [FrontendMasters] Production-Grade TypeScript**

<br/>

**Configured project :**  
https://github.com/mike-north/professional-ts-my-lib

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
  "env": { "node": true },
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": 2020,
    "project": "tsconfig.eslint.json"
  },
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking"
  ],
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
/build/
```
