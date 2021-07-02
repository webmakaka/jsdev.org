---
layout: page
title: React.js environment for development
description: Prepare environment for development react.js applications
keywords: react.js, environment, development
permalink: /env/react/
---

# React.js environment for development

**Taken from:**  
https://github.com/webmakaka/complete-intro-to-react-v6

<br/>

### <a href="/env/prettier/">Prettier</a>

### <a href="/env/react/eslint/">ESLint</a>

### <a href="/env/react/babel/">Babel</a>

<br/>

<br/>

### Absolute path imports for react apps

<br/>

**jsconfig.json**

<br/>

```json
{
  "compilerOptions": {
    "checkJs": true,
    "target": "es6",
    "baseUrl": "src"
  },
  "exclude": ["node_modules"]
}
```

<br/>

### Resolve src/ for Eslint

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

<br/>

    $ yarn add -D babel-eslint
