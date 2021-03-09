---
layout: page
title: Jest
description: Jest
keywords: env, jest
permalink: /env/jest/
---

<br/>

# Jest and Typescript config

<br/>

**Based on video course [FrontendMasters] Production-Grade TypeScript**

<br/>

**Configured project :**  
https://github.com/mike-north/professional-ts-my-lib

<br/>

```
$ npm install --save-dev \
    jest @types/jest \
    @babel/preset-env \
    @babel/preset-typescript
```

<br/>

    $ mkdir tests

<br/>

    $ vi tests/intex.test.ts

<br/>

**content**

https://github.com/mike-north/professional-ts-my-lib/blob/master/tests/index.test.ts

<br/>

    $ vi tests/tsconfig.json

```json
{
  "extends": "../tsconfig.json",
  "references": [
    {
      "name": "my-lib",
      "path": ".."
    }
  ],
  "compilerOptions": {
    "types": ["jest"],
    "rootDir": "..",
    "noEmit": true
  },
  "include": ["."]
}
```

<br/>

**.babelrc**

```json
{
  "presets": [
    ["@babel/preset-env", { "targets": { "node": 10 } }],
    "@babel/preset-typescript"
  ]
}
```

<br/>

```
$ npm run lint
$ npm run test
```
