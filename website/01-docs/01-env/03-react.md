---
layout: page
title: React.js environment for development
permalink: /env/react/
---

# React.js environment for development

Taken from:  
https://btholt.github.io/complete-intro-to-react-v5/

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

### Prettier

```
$ npm install --save-dev prettier
```

<br/>

**package.json**

```
"format": "prettier --write src/**/*.{js,html}",
"format:check": "prettier --list-different src/**/*.{js,html}"
```

<br/>

**Format on save document**

VSCode --> Preverences --> Extensions --> install --> Prettier - Code formatter esbenp.prettier-vscode

VSCode --> Preverences --> Settings:

- Format on Save (checked)
- Prettier Require Config --> require a prettier configuration file to foramt (checked)

<br/>

**<project_root> .prettierrc**

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

### ESLint


VSCode --> Preverences --> Extensions --> ESLint dbaeumer.vscode-eslint

<br/>

```
$ npm install --save-dev eslint eslint-config-prettier 
```
<!--

eslint-plugin-prettier

-->

<br/>

**.eslintrc**

```js
{
    "extends": [
    "eslint:recommended",
    "prettier",
    "prettier/react"
  ],
  "plugins": [],
  "parserOptions": {
    "ecmaVersion" : 2018,
    "sourceType" : "module",
    "ecmaFeatures": {
      "jsx" : true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  }
}

```

<!--

,
  "rules": {
    "no-extra-semi": "error",
    "semi": [2, "always"],
    "arrow-parens": [2, "always"]
  }
  
-->


<br/>

**package.json**

<br/>

```
"lint": "eslint src/**/*.{js,html} --quiet"
```

<!-- 

,
"lint:fix": "eslint --fix \"src/**/*.{js,jsx}\""

-->


<br/>

**.eslintignore**

<br/>

```
/node_modules/
```



### Parcel 


    $ npm install --save-dev parcel-bundler

<br/>

```
"dev": "parcel src/index.html"
```

<br/>

### React


    $ npm install --save react react-dom

<br/>

    $ npm install --save-dev \
                  babel-eslint \
                  eslint-plugin-import \
                  eslint-plugin-jsx-a11y \
                  eslint-plugin-react


    $ npm install --save-dev \
                  eslint-plugin-hooks



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
    "prettier/react"
  ],
  "rules": {
    "react/prop-types": 0,
    "no-console": 1,
    "react-hooks/rules-of-hooks": 2,
    "react-hooks/exhaustive-deps": 1
  },
  "plugins": ["react", "import", "jsx-a11y", "react-hooks"],
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
  },
  "settings": {
    "react": {
      "version":"detect"
    }
  }
}

```

<!--
    "jsx-a11y/label-has-for": 0,
-->


<!-- <br/>

**package.json**

```js
"lint": "./node_modules/.bin/eslint **/*.js",
"start": "npm run lint & nodemon server.js"
``` -->



<!--

<br/>

# Lint

```bash
$ npm install --save-dev eslint-config-react-app eslint-plugin-react
$ npm install --save-dev eslint-plugin-flowtype
$ npm install --save-dev babel-eslint
```


<br/>

    $ npm install --save-dev eslint eslint-config-prettier eslint-plugin-prettier






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

### JSHINT (Possible not needed)

**.jshintrc**

```js
{
  "predef": ["angular"]
}

"undef" : true, // Require all non-global variables be declared before they are used.
"strict" : true // Require `use strict` pragma in every file.

```
-->

<!--


<br/>



### Esling Standard

    $ npm install --save-dev eslint eslint-config-standard eslint-plugin-import eslint-plugin-node eslint-plugin-promise eslint-plugin-standard

<br/>

**.eslintrc**

<br/>

```js
{
  "extends": "standard",
  "rules": {
    "no-extra-semi": "error",
    "semi": [2, "always"]
  }
}
```

-->