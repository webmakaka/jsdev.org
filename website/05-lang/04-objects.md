---
layout: page
title: Objects
description: Objects
keywords: Objects
permalink: /lang/objects/
---

# Objects

```js
const p = {
  p1: 'value1',
  p2: 'value2',
  p3: 'value3',
};

for (const [key, value] of Object.entries(p)) {
  console.log(`${key}: ${value}`);
}
```

<br/>

```
const propertyNames = Object.keys(person);
const propertyValues = Object.values(person);
const entries = Object.entries(person);
```

<br/>

https://www.javascripttutorial.net/object/convert-an-object-to-an-array-in-javascript/

<br/>

### Find matches from one object to another

```js
function killer(suspectInfo, dead) {
  for (let [key, value] of Object.entries(suspectInfo)) {
    if (value.includes(...dead)) {
      return key;
    }
  }
}
```

```js
function killer(suspectInfo, dead) {
  return Object.keys(suspectInfo).find((x) =>
    dead.every((y) => suspectInfo[x].includes(y))
  );
}
```

https://www.codewars.com/kata/5f709c8fb0d88300292a7a9d/solutions/javascript

<br/>

```js
let array1 = [1, 2, 3],
  array2 = [1, 2, 3, 4],
  array3 = [1, 2];

let checker = (arr, target) => target.every((v) => arr.includes(v));

console.log(checker(array2, array1)); // true
console.log(checker(array3, array1)); // false
```

https://stackoverflow.com/questions/53606337/check-if-array-contains-all-elements-of-another-array

<br/>

```js
function combine(...obj) {
  const arrays = obj;

  let finalObject = {};

  for (let i = 0; i < arrays.length; i++) {
    for (let [key, value] of Object.entries(arrays[i])) {
      if (!(key in finalObject)) {
        finalObject[key] = value;
      } else {
        finalObject[key] = finalObject[key] + value;
      }
    }
  }

  return finalObject;
}
```

<br/>

### Array Of Objects

```js
function colourAssociation(array) {
  let res = [];

  for (let i = 0; i < array.length; i++) {
    // res[array[i][0]] = array[i][1];

    let obj = {};

    //console.log(array[i][0]);
    obj[array[i][0]] = array[i][1];
    res.push(obj);
  }

  console.log(res);
  return res;
}
```
