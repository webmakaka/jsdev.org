---
layout: page
title: React.js environment for development
permalink: /env/react/
---

# React.js environment for development

Taken from:  
https://btholt.github.io/complete-intro-to-react-v5/


Possible can be interesting:  
https://www.youtube.com/watch?v=SydnKbGc7W8


Possible can be helpful: 
https://glebbahmutov.com/blog/configure-prettier-in-vscode/

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

**.prettierrc**

```js
{
  "singleQuote": true,
  "bracketSpacing": true
}
```

<br>


**If needed to always use brackets for function with single argument (x) **

```
"arrowParens": "always",
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
    "prettier"
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

    $ npm install --save-dev \
                  babel-eslint \
                  eslint-plugin-import \
                  eslint-plugin-jsx-a11y \
                  eslint-plugin-react


    $ npm install --save-dev \
                  eslint-plugin-react-hooks



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


<br/>

** .ENV file (for absolute path) **

**.env**

```
NODE_PATH=src/
```

<br/>

### Resolve src/ 

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

### Run checks before commit (lint-staged husky)

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

### Babel

    $ npm install --save-dev babel-eslint

<br/>

**.eslintrc**

```
"parser": "babel-eslint",
```

<!-- 
<br/>

### Parcel 

    $ npm install --save-dev parcel-bundler

<br/>

```
"dev": "parcel src/index.html"
``` -->
