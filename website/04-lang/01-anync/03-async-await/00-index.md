---
layout: page
title: JavaScript Async/Await
description: JavaScript Async/Await
keywords: JavaScript Async/Await
permalink: /lang/async/async-await/
---

# JavaScript Async/Await

<br/>

### Easier Error Handling Using async await in JavaScript

https://www.youtube.com/watch?v=0iiZHlT0boc

https://medium.com/@jesterxl/easier-error-handling-using-async-await-b9ab0cb938e

<br/>

Nodejs app

<br/>

**func.js**

```js
const sureThing = (promise) =>
  promise
    .then((result) => ({ ok: true, result }))
    .catch((error) => Promise.resolve({ ok: false, error: error.message }));

const maybeCow = (animal) =>
  new Promise((success, failure) =>
    animal === 'cat'
      ? success('it is a cat')
      : failure(new Error(`it's not a cat, it is a: ${animal}`))
  );

const go = async (animal) => {
  const { ok, error, result } = await sureThing(maybeCow(animal));
  if (ok) {
    return { ok, result };
  } else {
    return { ok, error };
  }
};

export const result = go('cow');
```

<br/>

```js
import { result } from './func.js';

const res = await result;
console.log(res);
```

<br/>

**package.json**

```json
{...
  "type": "module",
...
}
```

<br/>

Resolve false

```
$ node index.js
{ ok: false, error: "it's not a cat, it is a: cow" }
```

<br/>

or

Resolve ok

```
$ node index.js
{ ok: true, result: 'it is a cat' }
```

<br/>

### Less interesting examples

<br/>

```js
const maybeCow = (cow) =>
  new Promise((success, failure) =>
    cow === 'cow'
      ? success('it is a cow')
      : failure(`it's not a cow, it is: ${cow}`)
  );

const go = async () => {
  const result = await maybeCow('cow');
  console.log('result: ', result);
};

go();
```

<br/>

```js
const maybeCow = (cow) =>
  new Promise((success, failure) =>
    cow === 'cow'
      ? success('it is a cow')
      : failure(`it's not a cow, it is: ${cow}`)
  );

const go = async () => {
  try {
    const result = await maybeCow('cow1');
    console.log('result: ', result);
  } catch (error) {
    console.log('error', error);
  }
};

go();
```

<br/>

### Another one sample

```js
const posts = [
  { title: 'Post One', body: 'This is post one' },
  { title: 'Post Two', body: 'This is post two' },
];

const getPosts = () => {
  console.log('GETTING DATA...');
  setTimeout(() => {
    posts.forEach((post, index) => {
      setTimeout(() => {
        console.log(index + 1, post.title, post.body);
      }, 2000 * (index + 1));
    });
  }, 1000);
};

const createPost = (post) => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      posts.push(post);
      const error = false;
      if (!error) {
        resolve();
      } else {
        reject('Error: Something went wrong');
      }
    }, 2000);
  });
};

const init = async () => {
  await createPost({ title: 'Post Three', body: 'This is post three' });
  getPosts();
};

init();
```

<br/>

### Another one sample

    $ npm init -y
    $ npm install node-fetch

```js
const fetch = require('node-fetch');

async function fetchUsers() {
  const res = await fetch('https://jsonplaceholder.typicode.com/users');
  const data = await res.json();
  console.log(data);
}

fetchUsers();
```

<br/>

https://www.youtube.com/watch?v=LrGvvvmRkCE

https://www.youtube.com/watch?v=IGoAdn-e5II
