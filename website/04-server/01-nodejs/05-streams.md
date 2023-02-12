---
layout: page
title: Node.JS Read Write Steams and Pipes
description: Node.JS Read Write Steams and Pipes
keywords: server, nodejs, streams, Read Write Steams and Pipes
permalink: /server/nodejs/streams/
---

# Node.JS Read Write Steams and Pipes

<br/>

### ReadStream

```js
const fs = require('fs');

const stream = fs.createReadStream('lorem.txt', 'utf-8');

let data = '';

// stream.on('data', part => {
//   console.log(part.length);
// });

stream.on('data', (part) => (data += part));
// stream.on('end', () => console.log('End', data.length));
stream.on('end', () => console.log('End', data));
stream.on('error', (error) => console.log('Error', error.message));
```

<br/>

### WriteStream

```js
const fs = require('fs');

const stream = fs.createReadStream('lorem.txt', 'utf-8');
const output = fs.createWriteStream('lorem.md');

let data = '';

stream.on('data', (part) => output.write(part));
stream.on('error', (error) => console.log('Error', error.message));
```

<br/>

### Pipe 1

```js
const fs = require('fs');

const input = fs.createReadStream('lorem.txt');
const output = fs.createWriteStream('lorem.md');

input.pipe(output);
```

<br/>

### Pipe 2

```js
const fs = require('fs');
const zlib = require('zlib');

const input = fs.createReadStream('lorem.txt');
const output = fs.createWriteStream('lorem.md.gz');
const gzip = zlib.createGzip();

input.pipe(gzip).pipe(output);

// class ReadStream {
//   pipe(stream) {
//     this.on('data', part => stream.write(part));
//     return stream;
//   }
// }
```
