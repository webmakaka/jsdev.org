---
layout: page
title: Node.JS Static Server
permalink: /server/nodejs/static-server/
---

# Node.JS Static Server

<br/>

https://www.npmjs.com/package/node-static

<br/>

    $ npm init -y
    $ npm install --save node-static

<br/>

    $ mkdir -p public
    $ vi ./public/index.html

<br/>

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Test</title>
    <meta charset="UTF-8" />
  </head>
  <body>
    <h1>WTF!</h1>
  </body>
</html>
```

<br/>

    $ vi server.js

<br/>

```js
var static = require('node-static');

const port = 8080;

const file = new static.Server('./public');

require('http')
  .createServer(function (request, response) {
    request
      .addListener('end', function () {
        file.serve(request, response);
      })
      .resume();
  })
  .listen(port, function () {
    console.log('Server started on port ' + port);
  });
```

<br/>

    $ node server.js

<br/>

    http://localhost:8080

<br/>

### Node.JS Static Server (with React app)

https://bitbucket.org/marley-react/The-Complete-React-Web-App-Developer-Course
