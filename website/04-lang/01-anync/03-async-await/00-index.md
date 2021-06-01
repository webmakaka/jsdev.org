---
layout: page
title: JavaScript Async/Await
description: JavaScript Async/Await
keywords: JavaScript Async/Await
permalink: /lang/async/async-await/
---

# JavaScript Async/Await

<br/>

**Async - Await**

Nodejs app

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

### Easier Error Handling Using async await in JavaScript

https://www.youtube.com/watch?v=0iiZHlT0boc

https://medium.com/@jesterxl/easier-error-handling-using-async-await-b9ab0cb938e

<br/>

https://www.youtube.com/watch?v=LrGvvvmRkCE

https://www.youtube.com/watch?v=IGoAdn-e5II
