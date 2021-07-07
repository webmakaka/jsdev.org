---
layout: page
title: React.js
description: React.js
keywords: React.js
permalink: /client/react/
---

# React.js

<br/>

### React official blog

https://facebook.github.io/react/blog/

<br/>

### React Lifecycle Methods diagram

http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/

<br/>

### Generate new react project

    # npm install -g npx
    $ npx create-react-app myapp

    // If typescript support is needed
    $ npx create-react-app myapp --typescript

<br/>

### Override default port for react app

```
"start": "PORT=8080 react-scripts start",
```

<br/>

### UI / CSS / Themes (/client/react/ui/)

<br/>

### React.js environment for development

[React.js environment for development](/env/react/)

[Create simple react project manually](/client/react/create-simple-react-project-manually/)

[React.js testing](/client/react/testing/)

[React.js And Bootstrap](https://www.youtube.com/watch?v=DyNADv8RZPs&list=PL_edDyMvX8wUK6BEeFPXdvfEgWl8RJnR_)

[Sass styles in create-react-app](https://www.youtube.com/watch?v=B_zZDa80FVo)

[Server Side Rendering](/client/react/ssr/)

[Spinners for react apps](http://www.davidhu.io/react-spinners/)

[Higher order components explained (HOC)](https://github.com/ZhangMYihua/higher-order-components-explained)

[Redux](/client/react/redux/)

<br/>

### Hooks (Since react 16)

[UseState](https://github.com/ZhangMYihua/use-state-example)

[UseEffect](https://github.com/ZhangMYihua/use-effect-example)

[useReducer](https://github.com/ZhangMYihua/useReducer-example)

[Custom hook example](https://github.com/ZhangMYihua/custom-hook-example)

[React context](https://github.com/ZhangMYihua/react-context-lesson)

<br/>

### Possible SPA routing script

```js
const express = require('express');
const path = require('path');

const server = express();

server.use(express.static('public'));

server.get('*', (req, res) => {
  fs.readFile(`${__dirname}/dist/index.html`, (err, html) => {
    if (error) throw error;

    res.setHeader('Content-Type', 'text/html');
    res.end(html);
  });
});

server.listen('8080', () => {
  console.log('Express listening on port 8080');
});
```
