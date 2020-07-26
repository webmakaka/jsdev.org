---
layout: page
title: GraphQL
description: GraphQL
keywords: GraphQL, Apollo Server, Apollo Client
permalink: /api/graphql/
---

# GraphQL

<br/>

### Installing Apollo Server and Graphql

    $ npm install apollo-server-express graphql
    $ npm install @types/graphql

<br/>

### Installing Apollo Client

    $ npm install apollo-boost react-apollo graphql
    $ npm install @types/graphql

<br/>

**package.json**

```js
{

    "scripts" : {
    "codegen:schema": "npx apollo client:download-schema --endpoint=http://localhost/api",
    "codegen:generate": "npx apollo client:codegen --localSchemaFile=schema.json --includes=src/**/*.tsx --target=typescript",

    }

}
```

<br/>

### [Udemy, Reed Barger] Full-Stack React with GraphQL and Apollo Boost [ENG, 2018]

https://github.com/webmakaka/Full-Stack-React-with-GraphQL-and-Apollo-Boost

<br/>

### [Udemy, Andrew Mead] The Modern GraphQL Bootcamp (Advanced Node.js) [ENG, 2018]

https://github.com/webmakaka/The-Modern-GraphQL-Bootcamp
