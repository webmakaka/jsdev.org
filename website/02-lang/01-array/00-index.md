---
layout: page
title: Arrays
description: Arrays
keywords: js, lang, Arrays
permalink: /lang/array/
---

# Arrays

<br/>

![development-process](/img/basics/array.jpg 'javascript array'){: .center-image }

<br/>

Array.pop - not pure. Do not recommend to use.  
Array.splice - not pure. Do not recommend to use.

<br/>

### [For](/lang/array/for/)

<br/>

### [Foreach](/lang/array/foreach/)

<br/>

### [Filter](/lang/array/filter/)

<br/>

### [Map](/lang/array/map/)

<br/>

### [Reduce](/lang/array/reduce/)

<br/>

### Join

<br/>

```json
const schools = [
    "Yorktown",
    "Washington & Lee",
    "Wakefield"
]
```

```js
console.log(schools.join(', '));
// "Yorktown, Washington & Lee, Wakefield"
```

<br/>

### Convert comma separated string to array

```js
var selections = [];
selections.push({ field: 'Year', selected: '2000, 2002, 2004, 2006, 2008' });

var field = selections['0'].field;
var selected1 = selections['0'].selected;

var temp1 = new Array();
temp1 = selected1.split(',');

// res ["2000", " 2002", " 2004", " 2006", " 2008"]

var temp2 = new Array();
temp2 = selected1.split(',').map(function (item) {
  return parseInt(item, 10);
});

// res [2000, 2002, 2004, 2006, 2008]
```

<br/>

### Example 2

```js
var selections = [];
selections.push({
  field: 'Territory code',
  selected: 'ABW, AFG, AGO, AIA, ALB',
});

var field1 = selections['0'].field;
var selected1 = selections['0'].selected;

var temp = new Array();
temp = selected1.split(',');

console.log('temp');
console.log(temp);

var res = [];

for (var i = 0; i < temp.length; i++) {
  // console.log(temp[i]);
  res.push({ qText: temp[i].trim() });
}

// res:

[
  {
    qText: 'ABW',
  },
  {
    qText: 'AFG',
  },
  {
    qText: 'AGO',
  },
  {
    qText: 'AIA',
  },
  {
    qText: 'ALB',
  },
];
```

<br/>

### Create an Array of Object programmatically

```js
self.processLocationData = function (data) {
  var res = [];

  for (var i = 0; i < data.items.length; i++) {
    res.push({
      StartDate: rimLibs.dateFormatDefault(new Date(data.items[i].StartDate)),
      EndDate: rimLibs.dateFormatDefault(new Date(data.items[i].EndDate)),
      Item: data.items[i].Item,
    });
  }

  self.observableDatasource(res);
  document.getElementById('ring-container').style.display = 'none';
  document.getElementById('chart-container').style.display = 'inline';
};
```

<br/>

### SPREAD

```js

const arr = [1,2,3];
const arr2 = [...arr, 4];

console.log(arr2);

---

const person1 = {
    name: 'Brad',
    age: 36
}

const person2 = {
    ...person1,
    email: 'brad@gmai.com'
}

console.log(person2);


---

const arr3 = [..arr.filter(num => num !== 2)];
console.log(arr3);

```

<br/>

### DESTRUCTURING

```js
const profile = {
  name: 'John Doe',
  address: {
    street: '40 Main st',
    city: 'Boston',
  },
  hobbies: ['movies', 'music'],
};

const { name, address, hobbies } = profile;
const { street, city } = profile.address;

console.log(name, address.street, hobbies[0]);
console.log(street, city);
```

<br/>

### CLASSES

```js
class Person {
  constructor(name, age) {
    console.log('run');
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age}`;
  }
}

const person1 = new Person('John', 33);
const person2 = new Person('Sara', 28);

console.log(person1.age);
console.log(person1.greet());
```

<br/>

### SUBCLASSES

```js
class Customer extends Person {
  constructor(name, age, balance) {
    console.log('run');
    super(name, age);
    this.balance = balance;
  }

  info() {
    return `${this.name} owes $${this.balance}.00`;
  }
}

const customer1 = new Customer('Kevin', 32, 300);

console.log(customer1.info());
```

<br/>

### MODULES

```js
// file1.js

export const name = 'Jeff';
export const nums = [1, 2, 3];
export default Person;

// file2.js

import { name, nums } from './file1.js';
import Person from './file1.js';

console.log(name, nums);
console.log(Person);
```

<br/>

### Remove single element from Array

```js
function findMissing(arr1, arr2) {
  let arr = arr1;

  for (let i = 0; i < arr2.length; i++) {
    let index = arr.indexOf(arr2[i]);

    if (index > -1) {
      arr.splice(index, 1);
    }
  }

  return arr[0];
}
```

https://www.codewars.com/kata/5a5915b8d39ec5aa18000030/solutions/javascript
