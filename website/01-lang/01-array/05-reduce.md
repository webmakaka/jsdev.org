---
layout: page
title: Array reduce
description: Array reduce
keywords: js, lang, array, reduce
permalink: /lang/array/reduce/
---

# Array reduce

<br/>

sample 1

```js
const ages = [21, 18, 42, 40, 64, 63, 34];
const maxAge = ages.reduce((max, age) => {
  console.log(`${age} > ${max} = ${age > max}`);
  if (age > max) {
    return age;
  } else {
    return max;
  }
}, 0);
console.log('maxAge', maxAge);
```

<br/>

sample 2

```js
const ages = [21, 18, 42, 40, 64, 63, 34];
// less syntax
const max = ages.reduce((max, value) => (value > max ? value : max), 0);
console.log('max', max);
```

<br/>

sample 3

```js
const colors = [
  {
    id: '-xekare',
    title: 'rad red',
    rating: 3,
  },
  {
    id: '-jbwsof',
    title: 'big blue',
    rating: 2,
  },
  {
    id: '-prigbj',
    title: 'grizzly grey',
    rating: 5,
  },
  {
    id: '-ryhbhsl',
    title: 'banana',
    rating: 1,
  },
];
const hashColors = colors.reduce((hash, { id, title, rating }) => {
  hash[id] = { title, rating };
  return hash;
}, {});
console.log(hashColors);
```

<br/>

sample 4

```js
const colors = ['red', 'red', 'green', 'blue', 'green'];
const distinctColors = colors.reduce(
  (distinct, color) =>
    distinct.indexOf(color) !== -1 ? distinct : [...distinct, color],
  []
);
console.log(distinctColors);
```

<br/>

**Links:**

https://github.com/MoonHighway/learning-react/tree/master/chapter-03
