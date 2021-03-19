---
layout: page
title: Prettier
description: Prettier
keywords: Prettier
permalink: /env/prettier/
---

# Prettier

<br/>

```
$ npm install --save-dev prettier
```

**.prettierrc**

```js
{
  "tabWidth": 2,
  "printWidth": 80,
  "semi": true,
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

**package.json**

```
"format": "prettier --write src/**/*.{js,html}",
"format:check": "prettier --list-different src/**/*.{js,html}"
```
