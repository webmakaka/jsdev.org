---
layout: page
title: React.js Typescript environment for development
description: Prepare environment for development react.js with TypeScript applications
keywords: react, typescript, environment, development
permalink: /env/react/typescript/
---

# Prepare environment for development react.js with TypeScript applications

<br/>

Based on course https://btholt.github.io/complete-intro-to-react-v6/eslint

<!--
  [UI Dev] React with TypeScript and
-->

<br/>

```
$ npm init -y
$ npm install --save-dev \
  typescript \
  @types/react \
  @types/react-dom \
  @types/react-router-dom
```

<br/>

```
$ npx tsc --init
```

<br/>

```json
"strict": true,
"lib": ["ESNext", "DOM"],
"jsx": "react-jsx",
"outDir": "./build",
```

<!--

<br/>

**tsconfig.dev.json**

```json
{
  "extends": "./tsconfig.json,
  "compilerOptions": {
    "jsx": "react-jsxdev"
  }
}
```

-->

<br/>

```
$ npm uninstall @babel/eslint-parser
```

<br/>

```
$ npm install -D eslint-import-resolver-typescript@2.4.0 @typescript-eslint/eslint-plugin@4.16.1 @typescript-eslint/parser@4.16.1
```

<br/>

**package.json**

<br/>

```
"lint": "eslint \"src/**/*.{js,jsx,ts,tsx}\" --quiet"
```

<br/>

**.eslintrc.json**

<br/>

```
// inside extends, above prettier rules
"plugin:@typescript-eslint/recommended",

// inside rules, generally a good rule but we're going to disable it for now
"@typescript-eslint/no-empty-function": 0

// inside plugins
"@typescript-eslint"

// replace parser
"parser": "@typescript-eslint/parser",

// add to settings array
"import/parsers": {
  "@typescript-eslint/parser": [".ts", ".tsx"]
},
"import/resolver": {
  "typescript": {
    "alwaysTryTypes": true
  }
}
```

<br/>

```
// under plugin:@typescript-eslint/recommended
"plugin:@typescript-eslint/recommended-requiring-type-checking",
```

<br/>

https://github.com/webmakaka/citr-v6-project/tree/master/typescript-1
