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

**Nodejs app**

<br/>

```js
const sureThing = (promise) =>
  promise
    .then((result) => ({ ok: true, result }))
    .catch((error) => Promise.resolve({ ok: false, error: error.message }));

const maybeCow = (animal) =>
  new Promise((success, failure) =>
    animal === 'cat'
      ? success('it is a cat')
      : failure(new Error(`it's not a cat, it is a ${animal}`))
  );

const go = async (animal) => {
  const { ok, error, result } = await sureThing(maybeCow(animal));
  if (ok) {
    return { ok, result };
  } else {
    return { ok, error };
  }
};

const result = async () => {
  const res = await go('dog');
  console.log(res);
};

result();
```

<br/>

**Alternative**

<br/>

```js
const sureThing = (promise) =>
  promise
    .then((result) => ({ ok: true, result }))
    .catch((error) => Promise.resolve({ ok: false, error: error.message }));

const maybeCow = (animal) =>
  new Promise((success, failure) =>
    animal === 'cat'
      ? success('it is a cat')
      : failure(new Error(`it's not a cat, it is a ${animal}`))
  );

const go = async (animal) => {
  const { ok, error, result } = await sureThing(maybeCow(animal));
  if (ok) {
    return { ok, result };
  } else {
    return { ok, error };
  }
};

const result = go('dog');

const res = await result;
console.log(res);
```

<br/>

**package.json**

type should be specified in package.json

```json
{...
  "type": "module",
...
}
```

<br/>

**Resolve false**

```
$ node index.js
{ ok: false, error: "it's not a cat, it is a dog" }
```

<br/>

or

**Resolve ok**

```
$ node index.js
{ ok: true, result: 'it is a cat' }
```

<br/>

### Less interesting example 1

<br/>

```js
const maybeCow = (animal) =>
  new Promise((success, failure) =>
    animal === 'cat'
      ? success('it is a cat')
      : failure(`it's not a cat, it is: ${animal}`)
  );

const go = async (animal) => {
  return await maybeCow(animal);
};

const result = go('cat');
const res = await result;
console.log(res);
```

<br/>

### Less interesting example 2

```js
const maybeCow = (animal) =>
  new Promise((success, failure) =>
    animal === 'cat'
      ? success('it is a cat')
      : failure(new Error(`it's not a cat, it is a ${animal}`))
  );

const go = async (animal) => {
  try {
    return await maybeCow(animal);
  } catch (error) {
    // console.log('error', error);
    return null;
  }
};

const result = go('dog');
const res = await result;

if (!res) {
  console.log('Something bad happened!');
  process.exit(1);
}

console.log(res);
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

<br/>

### Another one sample with UUID check

<br/>

```js
const isUUID = (id: any) => {
  // UUID
  const regexExp =
    /^[0-9a-fA-F]{8}\b-[0-9a-fA-F]{4}\b-[0-9a-fA-F]{4}\b-[0-9a-fA-F]{4}\b-[0-9a-fA-F]{12}$/gi;

  return new Promise((resolve, _reject) => {
    const res = regexExp.test(id);
    resolve(res);
  });
};
```

<br/>

```js
const uuidCorrect = await Utils.isUUID(id);

if (!uuidCorrect) {
  throw new Error('[Error] Invalid UUID');
}
```

<br/>

https://github.com/wildmakaka/rss-nodejs-2022-task3-crud-api
