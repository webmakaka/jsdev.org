---
layout: page
title: Loops
description: Loops
keywords: Loops
permalink: /lang/loops/
---

# Loops

<br/>

### for

```js
for (let i = 0; i < cars.length; i++) {
  text += cars[i] + '<br>';
}
```

<br/>

### while

```js
while (arr1.length > 0 || arr2.length > 0) {
  let el1 = arr1.pop();
  let el2 = arr2.pop();
  let temp = (el1 ? +el1 : 0) + (el2 ? +el2 : 0);
  result.push(temp);
}
```

<br/>

### Loop

```js
const loop = (times, callback) => {
  for (let i = 0; i < times; i++) {
    callback(i);
  }
};

loop(7, (i) => {
  console.log(`Iteration is #${i}`);
});
```
