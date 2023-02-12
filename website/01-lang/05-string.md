---
layout: page
title: String
description: String
keywords: String
permalink: /lang/string/
---

# String

<br/>

### forEach

<br/>

```js
const toBin = (inputDecimal) => {
  return Number(inputDecimal).toString(2);
};

var countBits = function (n) {
  let res = toBin(n);
  let count = 0;

  [...res].forEach((t) => {
    console.log(t);
    if (+t === 1) {
      count++;
    }
  });
  return count;
};
```
