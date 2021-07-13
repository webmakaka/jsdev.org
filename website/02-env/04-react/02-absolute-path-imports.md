---
layout: page
title: Absolute path imports for Node.js projects
description: Absolute path imports for Node.js projects
keywords: env, react, Absolute path imports
permalink: /env/react/absolute-path-imports/
---

# Absolute path imports for react apps

<br/>

**jsconfig.json**

<br/>

```json
{
  "compilerOptions": {
    "jsx": "react-jsx",
    "moduleResolution": "node",
    "checkJs": true,
    "module": "esnext",
    "target": "esnext",
    "baseUrl": "./src",
    "paths": {
      "~/*": ["./src/*"]
    }
  },
  "exclude": ["node_modules", "**/node_modules/*"],
  "include": ["./src/**/*.js"]
}
```

<br/>

### Resolve src/ for Eslint

<br/>

    $ yarn add -D babel-eslint

<br/>

**.eslintrc**

```
{
  "parser": "babel-eslint",
  "settings": {
    "import/resolver": {
      "node": {
        "paths": ["src"],
        "extensions": [".js", ".jsx", ".ts", ".tsx"]
      }
    }
  }
}
```

<!--

<br/>

### Babel (possible babel is not needed)

```
$ yarn add -D \
    @babel/core \
    @babel/node \
    @babel/cli \
    @babel/preset-env \
    babel-plugin-module-resolver
```

<br/>

**babel.config.json**

```js
{
  "presets": [["@babel/preset-env"]],
  "plugins": [
    [
      "module-resolver",
      {
        "root": ["./src"],
        "alias": {
          "~": "./src"
        }
      }
    ]
  ]
}
```


-->
