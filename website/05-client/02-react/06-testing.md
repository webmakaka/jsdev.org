---
layout: page
title: React.js testing
permalink: /client/react/testing/
---

# React.js testing

<br/>

### [Jest]

<br/>

### Enzyme

https://airbnb.io/enzyme/

    $ npm install --save-dev enzyme jest-cli react-test-renderer
    $ npm install --save-dev enzyme-adapter-react-16

<br/>

**src/setupTests.js**

```js
import { configure } from 'enzyme';
import Adapter from 'enzyme-adapter-react-16';

configure({ adapter: new Adapter() });
```

<br/>

** .eslintrc**

<br/>

```
"env": {

  ***
  "jest": true
  ***

}
```

<br/>

    $ npx jest
    $ npx jest --silent

<br/>

**package.json**

<br/>

````
"scripts": {

  ***
  "test": "jest --silent",
  "test:update": "jest --silent -u",
  "test:watch": "jest --silent --watch",
  "test:coverage": "jest --silent --coverage",
  ***

}

<br/>

### [LevelUpTuts] React Testing For Beginners

https://www.youtube.com/watch?v=esVwR4lGwQE&list=PLLnpHn493BHEqP3gD1pCJYhxX6v2gBZzj



<br/>

### Examples

<br/>

```js
import React from 'react';
import ReactDOM from 'react-dom';
import App from '../App';

it('shows a comment box', () => {

  const div =  document.createElement('div');
  ReactDOM.render(<App />, div);

  expect(div.innerHTML).toContain('Comment Box');

  ReactDOM.unmountComponentAtNode(div);
});
````

<br/>

```js
import React from 'react';
import { shallow } from 'enzyme';
import App from '../App';
import CommentBox from '../CommentBox';
import CommentList from '../CommentList';

let wrapped;

beforeEach(() => {
  wrapped = shallow(<App />);
});

it('shows a comment box', () => {
  expect(wrapped.find(CommentBox).length).toEqual(1);
});

it('shows a comment list', () => {
  expect(wrapped.find(CommentList).length).toEqual(1);
});
```

<br/>

```js
import React from 'react';
import { mount } from 'enzyme';
import CommentBox from '../CommentBox';

let wrapped;

beforeEach(() => {
  wrapped = mount(<CommentBox />);
});

afterEach(() => {
  wrapped.unmount();
});

it('has a text area and a button', () => {
  expect(wrapped.find('textarea').length).toEqual(1);
  expect(wrapped.find('button').length).toEqual(1);
});
```
