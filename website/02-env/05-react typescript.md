---
layout: page
title: React.js Typescript environment for development
description: Prepare environment for development react.js with TypeScript applications
keywords: react, typescript, environment, development
permalink: /env/react-typescript/
---

# Prepare environment for development react.js with TypeScript applications

<br/>

Based on course [UI Dev] React with TypeScript

<br/>

```
$ npm init -y
$ npm install --save-dev \
  typescript \
  @types/react \
  @types/react-dom
```

<br/>

```
$ npx tsc --init
```

<br/>

```
"lib": ["ESNext", "DOM"],
"jsx": "react-jsx",
"outDir": "./build",
```

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

<br/>
