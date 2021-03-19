---
layout: page
title: ESlint for React
description: ESlint for React
keywords: env, eslint, react
permalink: /env/eslint/react/
---

<br/>

# ESlint for React

https://btholt.github.io/complete-intro-to-react-v6/eslint

<br/>

```
$ npm install --save-dev \
  eslint \
  eslint-config-prettier
```

<!--
eslint-plugin-prettier
-->

<br/>

**.eslintrc**

```json
{
  "extends": ["eslint:recommended", "prettier"],
  "plugins": [],
  "parserOptions": {
    "ecmaVersion": 2021,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  }
}
```

<br/>

**package.json**

<br/>

```
"lint": "eslint src/**/*.{js,html} --quiet",
"lint:fix": "eslint --fix src/**/*.{js,html}",
```

<br/>

**.eslintignore**

<br/>

```
/node_modules/
```

<br/>

### React

<br/>

    $ npm install --save react react-dom

<br/>

### Absolute path imports for react apps

<br/>

**jsconfig.json**

<br/>

```json
{
  "compilerOptions": {
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
  "settings": {
    "import/resolver": {
      "node": {
        "paths": ["src"]
      }
    }
  }
}
```

<br/>

### ESLint + React

https://btholt.github.io/complete-intro-to-react-v6/jsx

<br/>

```
$ npm install --save-dev \
              eslint-plugin-import@2.22.1 \
              eslint-plugin-jsx-a11y@6.4.1 \
              eslint-plugin-react@7.22.0 \
              eslint-plugin-react-hooks


```

<br/>

**.eslintrc**

```js
{
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:react/recommended",
    "plugin:jsx-a11y/recommended",
    "prettier",
    "prettier/react",
    "plugin:react-hooks/recommended"
  ],
  "rules": {
    "react/prop-types": 0,
    "react/react-in-jsx-scope": 0
  },
  "plugins": ["react", "import", "jsx-a11y"],
  "parserOptions": {
    "ecmaVersion": 2021,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}

```

<br/>

### ESLint + React + Hooks

https://btholt.github.io/complete-intro-to-react-v6/hooks

<!--
    babel-eslint
-->

<br/>

```
$ npm install --save-dev \
              eslint-plugin-react-hooks
```

<br/>

```
{
  "extends": [
    …
    "plugin:react-hooks/recommended",
    …
  ]
}
```
