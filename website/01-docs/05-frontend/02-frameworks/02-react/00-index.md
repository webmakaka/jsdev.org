---
layout: page
title: React.js
permalink: /frontend/react/
---

# React

<br/>

### React official blog

https://facebook.github.io/react/blog/

<br/>

### Generate new react project

    # npm install -g npx
    $ npx create-react-app myapp

<br/>

### Override default port for react app

```
"start": "PORT=8080 react-scripts start",
```

<br/>

### React.js environment for development

[React.js environment for development](/env/react/)

[Create simple react project manually](/frontend/react/create-simple-react-project-manually/)

[React.js testing](/frontend/react/testing/)

[React.js Material UI](/frontend/react/material-ui/)

[React.js And Bootstrap](https://www.youtube.com/watch?v=DyNADv8RZPs&list=PL_edDyMvX8wUK6BEeFPXdvfEgWl8RJnR_)

[Sass styles in create-react-app](https://www.youtube.com/watch?v=B_zZDa80FVo)

[Server Side Rendering](/frontend/react/ssr/)

[Spinners for react apps](http://www.davidhu.io/react-spinners/)

<br/>

### Possible SPA routing script

```javascript
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
