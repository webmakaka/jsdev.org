---
layout: page
title: Example Promise
permalink: /lang/async/promises/example/
---

<br/>


# Example Promise

from course [Andrew Mead] The Complete Node.js Developer Course 2.0 (updated) [2018, ENG] 


**by standart callback**

{% highlight javascript linenos %}

function getTempCallback (location, callback) {
  callback(undefined, 78);
  callback('City not found');
}

getTempCallback('Philadelphia', function (err, temp) {
  if (err) {
    console.log('error', err);
  } else {
    console.log('success', temp)
  }
});

{% endhighlight %}

<br/>

**by promise**

{% highlight javascript linenos %}

function getTempPromise (location) {
  return new Promise(function (resolve, reject) {
    setTimeout(function () {
      resolve(79);
      reject('City not found');
    }, 1000);
  });
}

getTempPromise('Philadelphia').then(function (temp) {
  console.log('promise success', temp);
}, function (err) {
  console.log('promise error', err);
});

{% endhighlight %}


<br/>
<br/>

### Another example

{% highlight javascript linenos %}

// Challenge Area
function addPromise (a, b) {
  return new Promise(function (resolve, reject) {
    if (typeof a === 'number' && typeof b === 'number') {
      resolve(a + b);
    } else {
      reject('A & b need to be numbers');
    }
  });
}

addPromise(2, 3).then(function (sum) {
  console.log('success', sum);
}, function (err) {
  console.log('error', err);
});

addPromise('andrew', 9).then(function (sum) {
  console.log('this should not show up');
}, function (err) {
  console.log('This should appear', err);
});

{% endhighlight %}



<br/>
<br/>

### How to Chain JavaScript Promises
https://html5hive.org/how-to-chain-javascript-promises/
