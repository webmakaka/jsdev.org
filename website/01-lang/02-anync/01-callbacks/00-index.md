---
layout: page
title: JavaScript Callbacks
description: JavaScript Callbacks
keywords: lang, async, callbacks
permalink: /lang/async/callbacks/
---

# JavaScript Callbacks

https://www.youtube.com/watch?v=PoRJizFvM7s

<br/>

**Callbacks**

<br/>

```js
const posts = [
  { title: 'Post One', body: 'This is post one' },
  { title: 'Post Two', body: 'This is post two' },
];

function getPosts() {
  setTimeout(() => {
    let output = '';
    posts.forEach((post, index) => {
      output += `<li>${post.title}</li>`;
    });
    document.body.innerHTML = output;
  }, 1000);
}

function createPost(post, callback) {
  setTimeout(() => {
    post.push(post);
    callback();
  }, 2000);
}

getPosts();

createPost({ title: 'Post Three', body: 'This is post three' }, getPosts);
```

