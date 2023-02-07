---
layout: page
title: Arrays
description: Arrays
keywords: Arrays
permalink: /lang/arrays/2/
---

# Arrays

<br/>

### FOREACH

```js
const fruits = ['Apples', 'Oranges', 'Grapes'];

fuits.forEach((fruit, index) => {
  console.log(fruit);
});
```

<br/>

### MAP

```js
const singleFruit = fruits.map((fruit) => fruit.slice(0, -1));
console.log(singleFruit);
```

<br/>

### FILTER

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

<br/>

### Array to String

```js
myArray.join(' ');
```
