---
layout: page
title: Jest
description: Jest
keywords: env, jest
permalink: /env/nodejs/typescript/jest/
---

<br/>

# Jest and Typescript config

<br/>

**Configuring Jest**  
https://jestjs.io/docs/configuration

<br/>

I think need to exclude jest config from package.json

<br/>

And run tests command like:

```
"test": "NODE_PATH=./src jest --config ./test/jest-e2e.json"
```

<!--

```
,
  "jest": {
    "moduleFileExtensions": [
      "js",
      "json",
      "ts"
    ],
    "rootDir": "src",
    "testRegex": ".*\\.spec\\.ts$",
    "transform": {
      "^.+\\.(t|j)s$": "ts-jest"
    },
    "collectCoverageFrom": [
      "**/*.(t|j)s"
    ],
    "coverageDirectory": "../coverage",
    "testEnvironment": "node"
  }
```

-->

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

    $ vi tests/index.test.ts

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
