---
layout: page
title: WebPack - Basics
description: WebPack - Basics
keywords: WebPack - Basics
permalink: /env/build/webpack/basics/
---

# WebPack - Basics

    # cd project
    # mkdir js_modules
    # cd js_modules
    # npm init -f

or

    # npm init -y

<br/>

    // Possible will work only with version 2.x
    # yarn add -D webpack webpack-cli
    # touch webpack.config.js

<br/>

    # vi webpack.config.js

<br/>

```js
const path = require('path');

const config = {
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'build'),
    filename: 'bundle.js',
  },
};

module.exports = config;
```

<br/>

    # vi package.json

<br/>

```json
"scripts": {
    "build": "webpack"
},
```

<br/>

    # vi src/index.js

<br/>

```js
const sum = require('./sum');

const total = sum(10, 5);

console.log(total);
```

<br/>

    # vi src/sum.js

<br/>

```js
const sum = (a, b) => a + b;

module.exports = sum;
```

<br/>

```
<html>
<head>

</head>
<body>
    <script src="build/bundle.js"></script>
</body>
</html>
```

<br/>

    # npm run build
