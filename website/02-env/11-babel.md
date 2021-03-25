---
layout: page
title: Babel
description: Babel
keywords: env, babel
permalink: /env/babel/
---

<br/>

# Babel

https://btholt.github.io/complete-intro-to-react-v6/babel

```
$ npm install -D @babel/core@7.12.16 @babel/preset-react@7.12.13
```

<br/>

**.babelrc**

<br/>

```json
{
  "presets": [
    [
      "@babel/preset-react",
      {
        "runtime": "automatic"
      }
    ]
  ]
}
```

<br/>

    $ npm install --save-dev babel-eslint

<br/>

**.eslintrc**

```
"parser": "babel-eslint",
```

<br/>

### Additional Class Properties (If needed)

https://btholt.github.io/complete-intro-to-react-v6/class-properties

<br/>

```
$ npm install -D @babel/plugin-proposal-class-properties @babel/preset-env @babel/eslint-parser
```

<br/>

**.babelrc**

```
{
  "presets": [
    [
      "@babel/preset-react",
      {
        "runtime": "automatic"
      }
    ],
    "@babel/preset-env"
  ],
  "plugins": ["@babel/plugin-proposal-class-properties"]
}

```

<br/>

**.eslintrc.json**

```
{
  …
  "parser": "@babel/eslint-parser",
  …
}
```
