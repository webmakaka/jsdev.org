---
layout: page
title: Nodemon
description: Nodemon
keywords: Nodemon
permalink: /env/nodemon/
---

# Nodemon

**nodemon.json**

<br/>

```json
{
  "ignore": ["node_modules"],
  "watch": ["./src/**/*.ts"],
  "exec": "npm start",
  "ext": "ts"
}
```

<br/>

**package.json**

```json
{
  "build": "NODE_PATH=./src tsc",
  "start": "NODE_PATH=./src ts-node src/server.ts",
  "dev": "NODE_PATH=./src nodemon"
}
```

<br/>

    $ npm run dev
