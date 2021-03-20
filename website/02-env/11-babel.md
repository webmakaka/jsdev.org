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
