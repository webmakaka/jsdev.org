---
layout: page
title: Deploy React App
description: Deploy React App
keywords: client, react, deploy
permalink: /client/react/deploy/
---

# Deploy React App

### Deploy Node.js and React Apps | Full Deployment /w Nginx VPS, SSL

https://www.youtube.com/watch?v=Nxw2j1-srVc

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
