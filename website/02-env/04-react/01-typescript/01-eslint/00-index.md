---
layout: page
title: Next.js environment for development
description: Prepare environment for development next.js applications
keywords: nest.js, environment, development, eslint
permalink: /env/next/typescript/eslint/
---

# Eslint config for Next.js + TypeScript applications

<br/>

```
$ yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin  
eslint-plugin-react-hooks
```

<br/>

**.eslintrc**

<br/>

```json
{
  "root": true,
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"],
  "rules": {
    "semi": "off",
    "@typescript-eslint/semi": ["warn"],
    "@typescript-eslint/no-empty-interface": [
      "error",
      {
        "allowSingleExtends": true
      }
    ]
  },
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:react-hooks/recommended"
  ]
}
```
