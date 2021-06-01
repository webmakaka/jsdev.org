---
layout: page
title: Example Promise
description: Example Promise
keywords: Example Promise
permalink: /lang/async/promises/example/
---

<br/>

# Example Promise

https://www.youtube.com/watch?v=PoRJizFvM7s

<br/>

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

createPost({ title: 'Post Three', body: 'This is post three' })
  .then(getPosts)
  .catch((err) => console.log(err));
```

<br/>

```js
const fetch = require('node-fetch');

const promise1 = new Promise((resolve) => {
  resolve('Hello World');
});

const promise2 = 10;

const promise3 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('Goodbye');
  }, 2000);
});

const promise4 = fetch('https://jsonplaceholder.typicode.com/users').then(
  (res) => res.json()
);

Promise.all([promise1, promise2, promise3, promise4]).then((values) =>
  console.log(values)
);
```

<br/>

From course [Andrew Mead] The Complete Node.js Developer Course 2.0 (updated) [ENG, 2018]

**by standart callback**

```javascript
function getTempCallback(location, callback) {
  callback(undefined, 78);
  callback('City not found');
}

getTempCallback('Philadelphia', function (err, temp) {
  if (err) {
    console.log('error', err);
  } else {
    console.log('success', temp);
  }
});
```

<br/>

**by promise**

```javascript
function getTempPromise(location) {
  return new Promise(function (resolve, reject) {
    setTimeout(function () {
      resolve(79);
      reject('City not found');
    }, 1000);
  });
}

getTempPromise('Philadelphia').then(
  function (temp) {
    console.log('promise success', temp);
  },
  function (err) {
    console.log('promise error', err);
  }
);
```

<br/>
<br/>

### Another example

```javascript
// Challenge Area
function addPromise(a, b) {
  return new Promise(function (resolve, reject) {
    if (typeof a === 'number' && typeof b === 'number') {
      resolve(a + b);
    } else {
      reject('A & b need to be numbers');
    }
  });
}

addPromise(2, 3).then(
  function (sum) {
    console.log('success', sum);
  },
  function (err) {
    console.log('error', err);
  }
);

addPromise('andrew', 9).then(
  function (sum) {
    console.log('this should not show up');
  },
  function (err) {
    console.log('This should appear', err);
  }
);
```

<br/>
<br/>

### How to Chain JavaScript Promises

https://html5hive.org/how-to-chain-javascript-promises/
