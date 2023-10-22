---
layout: page
title: Array map
description: Array map
keywords: js, lang, array, map
permalink: /lang/array/map/
---

# Array map

<br/>

```json
const schools = [
    "Yorktown",
    "Washington & Lee",
    "Wakefield"
]
```

<br/>

sample 1

```js
const highSchools = schools.map((school) => `${school} High School`);

console.log(highSchools.join('\n'));
// Yorktown High School
// Washington & Lee High School
// Wakefield High School

console.log(schools.join('\n'));
// Yorktown
// Washington & Lee
// Wakefield
```

<br/>

sample 2

```js
const highSchools = schools.map((school) => ({ name: school }));
console.log(highSchools);
// [
// { name: "Yorktown" },
// { name: "Washington & Lee" },
// { name: "Wakefield" }
// ]
```

<br/>

sample 3

```js
let schools = [
  { name: 'Yorktown' },
  { name: 'Stratford' },
  { name: 'Washington & Lee' },
  { name: 'Wakefield' },
];
const editName = (oldName, name, arr) =>
  arr.map((item) => {
    if (item.name === oldName) {
      return {
        ...item,
        name,
      };
    } else {
      return item;
    }
  });
let updatedSchools = editName('Stratford', 'HB Woodlawn', schools);
console.log(updatedSchools[1]);
console.log(schools[1]);
```

    or

```js
const editName = (oldName, name, arr) =>
  arr.map((item) => (item.name === oldName ? { ...item, name } : item));
```

<br/>

sample 4

```js
const schools = {
  Yorktown: 10,
  'Washington & Lee': 2,
  Wakefield: 5,
};
const schoolArray = Object.keys(schools).map((key) => ({
  name: key,
  wins: schools[key],
}));
console.log(schoolArray);
```

<br/>

### Another Example

```js
const fruits = ['Apples', 'Oranges', 'Grapes'];

const singleFruit = fruits.map((fruit) => fruit.slice(0, -1));
console.log(singleFruit);
```
