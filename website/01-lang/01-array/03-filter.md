---
layout: page
title: Array Filter
description: Array Filter
keywords: js, lang, array, filter
permalink: /lang/array/filter/
---

# Array Filter

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
const wSchools = schools.filter((school) => school[0] === 'W');
console.log(wSchools);
// ["Washington & Lee", "Wakefield"]
```

<br/>

sample 2

```js
const cutSchool = (cut, list) => list.filter((school) => school !== cut);

console.log(cutSchool('Washington & Lee', schools).join(' * '));
// "Yorktown * Wakefield"

console.log(schools.join('\n'));
// Yorktown
// Washington & Lee
// Wakefield
```

<br/>

### Next Example

```js
const people = [
  { id: 1, name: 'Karen' },
  { id: 2, name: 'Bob' },
  { id: 3, name: 'Sharon' },
];

// momove Bob from array

const people2 = people.filter((person) => person.id !== 2);
confole.log(people2);
```
