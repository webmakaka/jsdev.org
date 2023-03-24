---
layout: page
title: Dates
description: Dates
keywords: js, lang, dates
permalink: /lang/dates/
---

# Dates

<br/>

### unhappyDays in the year

```js
describe('Basic Tests', () => {
  Test.assertEquals(unluckyDays(1586), 1, 'should be: 1');
  Test.assertEquals(unluckyDays(1001), 3, 'should be: 3');
  Test.assertEquals(unluckyDays(2819), 2, 'should be: 2');
  Test.assertEquals(unluckyDays(2792), 2, 'should be: 2');
  Test.assertEquals(unluckyDays(2723), 2, 'should be: 2');
  Test.assertEquals(unluckyDays(1909), 1, 'should be: 1');
  Test.assertEquals(unluckyDays(1812), 2, 'should be: 2');
  Test.assertEquals(unluckyDays(1618), 2, 'should be: 2');
  Test.assertEquals(unluckyDays(2132), 1, 'should be: 1');
  Test.assertEquals(unluckyDays(2065), 3, 'should be: 3');
});
```

```js
function unluckyDays(year) {
  let unhappyDays = 0;

  const weekday = [
    'Sunday',
    'Monday',
    'Tuesday',
    'Wednesday',
    'Thursday',
    'Friday',
    'Saturday',
  ];

  for (let i = 0; i < 12; i++) {
    const month = i;
    const d = new Date(year, month, 13);
    if (weekday[d.getDay()] === 'Friday') {
      unhappyDays++;
    }
  }

  return unhappyDays;
}
```
