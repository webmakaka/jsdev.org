---
layout: page
title: React.js environment for development
permalink: /frontend/react/env/
---

# React.js environment for development

<br/>

### Prepare docker container for development

[Prepare docker container for development](/env/docker/run-container/linux/)

<br/>

### React

<!-- <br/>

**vscode**

```
{
  "editor.fontSize": 26,
  "editor.tabSize": 2,
  "editor.wordWrap": "on",
  "terminal.integrated.fontSize": 26,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
  "emmet.syntaxProfiles": {
    "javascript": "jsx"
  },
  "editor.formatOnSave": true,
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 10000,
  "gitlens.advanced.messages": {
    "suppressShowKeyBindingsNotice": true
  },
  "diffEditor.ignoreTrimWhitespace": false,
  "[javascript]": {
    "editor.formatOnSave": false
  },
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
  "prettier.requireConfig": true,
  "prettier.disableLanguages": ["js"],
  "prettier.singleQuote": true
}
``` -->

<br/>

# .ENV

**.env**

```
NODE_PATH=src/
```

<br/>

# Prettier

```
$ npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier
```

<br/>

**package.json**

```
"format": "prettier --write src/**/*.{js,jsx,css,json}",
"format:check": "prettier --list-different src/**/*.{js,jsx,css,json}"
```

<br/>

**.prettierrc**

```js
{
  "singleQuote": true,
  "arrowParens": "always",
  "bracketSpacing": true
}
```

<br/>

**.prettierignore**

```
node_modules
*.test.js
*.spec.js
```

<br/>

# Lint

```bash
$ npm install --save-dev eslint-config-react-app eslint-plugin-react
$ npm install --save-dev eslint-plugin-jsx-a11y
$ npm install --save-dev eslint-plugin-flowtype
$ npm install --save-dev babel-eslint
```

<br/>

**.eslintrc**

<!-- ```js
{
  "extends": ["react-app", "plugin:prettier/recommended"],
  "rules": {
    "no-extra-semi": "error",
    "semi": [2, "always"],
    "arrow-parens": [2, "always"]
  }
}

``` -->

<!--

react video course
React for beginners

-->

```js
{
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:react/recommended",
    "plugin:jsx-a11y/recommended",
    "prettier",
    "prettier/react"
  ],
  "rules": {
    "react/prop-types": 0,
    "jsx-a11y/label-has-for": 0,
    "no-console": 1
  },
  "plugins": ["react", "import", "jsx-a11y"],
  "parserOptions": {
    "ecmaVersion": 2018,
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

    $ npm install --save-dev eslint eslint-config-prettier eslint-plugin-prettier

    $ npm install --save-dev babel-eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react

<br/>

**package.json**

<br/>

```
"lint": "eslint \"src/**/*.{js,jsx}\"",
"lint:fix": "eslint --fix \"src/**/*.{js,jsx}\""
```

<br/>

**.eslintignore**

<br/>

```
/node_modules/
```

<!-- <br/>

**package.json**

```js
"lint": "./node_modules/.bin/eslint **/*.js",
"start": "npm run lint & nodemon server.js"
``` -->

<br/>

# lint-staged husky

```bash
$ npm install --save-dev lint-staged husky
```

**package.json**

```json

  "scripts": {
    ******
    "precommit": "lint-staged"
  },
  "devDependencies": {
    ********
  },
  "lint-staged": {
    "*.{js, jsx}": ["node_modules/.bin/eslint --max-warnings=0", "prettier --write", "git add"]
  }
}
```

<br/>

# Babel

    $ npm install --save-dev babel-eslint babel-core babel-preset-env babel-plugin-transform-class-properties

<br/>

**.babelrc**

<br/>

```js
{
  "presets": [
    [
      "env",
      {
        "targets": {
          "browsers": ["last 2 versions"]
        }
      }
    ]
  ],
  "plugins": ["transform-class-properties"]
}
```

<br/>

**.eslintrc**

```js
{
  …
  "parser": "babel-eslint",
  …
}
```

<br/>

taken it here:

<br/>

https://btholt.github.io/complete-intro-to-react-v4/async-and-events-in-react

<br/>

### JSHINT (Possible not needed)

**.jshintrc**

```js
{
  "predef": ["angular"]
}

"undef" : true, // Require all non-global variables be declared before they are used.
"strict" : true // Require `use strict` pragma in every file.

```
