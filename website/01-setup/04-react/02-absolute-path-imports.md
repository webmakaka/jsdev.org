---
layout: page
title: Absolute path imports for Node.js projects
description: Absolute path imports for Node.js projects
keywords: env, react, Absolute path imports
permalink: /setup/react/absolute-path-imports/
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

Actually ~/\* is not working for now in the box. Need to make eject or install additional packages like craco.

https://stackoverflow.com/questions/63067555/how-to-make-an-import-shortcut-alias-in-create-react-app

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
