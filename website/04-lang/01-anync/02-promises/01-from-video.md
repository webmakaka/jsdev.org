---
layout: page
title: Example Promise From Video
description: Example Promise From Video
keywords: Example Promise From Video
permalink: /lang/async/promises/from-video/
---

# Example Promise From Video

Mastering JavaScript Series: Promises

https://www.wintellectnow.com/Videos/Watch?videoId=promises-in-javascript

<br/>

### resolve

{% highlight javascript linenos %}

<!DOCTYPE html>

<script>

    'use strict';

    const p = new Promise((resolve, reject) => {
        setTimeout( () => {
            resolve();
        }, 2000);
    });

    console.log('waiting');

    p.then(() => {
        console.log('promise is resolved');
    });

</script>

</html>

{% endhighlight %}

<br/>

### reject

{% highlight javascript linenos %}

<!DOCTYPE html>

<script>

    'use strict';

    const p = new Promise((resolve, reject) => {
        setTimeout( () => {
            reject();
        }, 2000);
    });

    console.log('waiting');

    p.then(() => {
        console.log('promise is resolved');
    }).catch(() => {
        console.log('promise is rejected');
    });

</script>

</html>

{% endhighlight %}

<br/>

### resolve / reject with data

```javascript

<!DOCTYPE html>

<script>

    'use strict';

    const p = new Promise((resolve, reject) => {
        setTimeout( () => {
            // resolve('success!');
            reject('failure');
        }, 2000);
    });

    console.log('waiting');

    p.then(results => {
        console.log('promise is resolved');
        console.log(results);
    }).catch(results => {
        console.log('promise is rejected');
        console.log(results);
    });

</script>

</html>

```

<br/>

{% highlight javascript linenos %}

Promise.resolve('some value').then(results => console.log(results));
Promise.reject('some value').catch(results => console.log(results));

{% endhighlight %}

<br/>

<br/>

### Chaining

{% highlight javascript linenos %}

setTimeout(() => {
console.log('a');

    setTimeout(() => {
        console.log('b');
    }, 2000);

}, 2000);

{% endhighlight %}

<br/>

<br/>

{% highlight javascript linenos %}

const p = new Promise( resolve => {

    setTimeout(() => {
        console.log('a');
        resolve('a is done');
    }, 2000);

});

    p.then(results => {
        console.log(results);
        return new Promise (resolve => {
            setTimeout(() => {
                console.log('b');
                resolve('b is done');
            }, 2000);
        });

    }).then(results => {
        console.log(results);
        console.log('all done');
    });

    console.log('waiting...');

{% endhighlight %}

<br/>

Results:

<br/>

    waiting
    a
    a is done
    b
    b is done
    all done

<br/>

<br/>

### Try Catch Finnaly Async

<br/>

{% highlight javascript linenos %}

<script>

    'use strict';

    let doAsyncCallCounter = 0;

    const doAsync = doesResolve => new Promise((resolve, reject) => {

        doAsyncCallCounter++;

        setTimeout(() => {
            if (doesResolve){
                resolve('success!', doAsyncCallCounter);
            } else {
                resolve('failure!', doAsyncCallCounter);
            }
        }, 2000);
    });

    doAsync(true).then(results => {
        console.log(results);
    });

</script>

{% endhighlight %}

<br/>

{% highlight javascript linenos %}

<script>

    'use strict';

    let doAsyncCallCounter = 0;

    const doAsync = doesResolve => new Promise((resolve, reject) => {

        doAsyncCallCounter++;

        setTimeout(() => {
            if (doesResolve){
                console.log('success', doAsyncCallCounter);
                resolve({ msg: 'success!', counter: doAsyncCallCounter });
            } else {
                console.log('failure', doAsyncCallCounter);
                reject({ msg: 'failure!', counter: doAsyncCallCounter });
            }
        }, 2000);
    });

    doAsync(true)
        .then(() => doAsync(true))
        .then(() => doAsync(false))
        .then(() => doAsync(true))
        .then(() => doAsync(true))
        .catch(err => {
            console.log(err);
        },() => {
            console.log('finally');
        });

</script>

{% endhighlight %}

<br/>

{% highlight javascript linenos %}

<script>

    'use strict';

    let doAsyncCallCounter = 0;

    const doAsync = doesResolve => new Promise((resolve, reject) => {

        doAsyncCallCounter++;

        setTimeout(() => {
            if (doesResolve){
                console.log('success', doAsyncCallCounter);
                resolve({ msg: 'success!', counter: doAsyncCallCounter });
            } else {
                console.log('failure', doAsyncCallCounter);
                reject({ msg: 'failure!', counter: doAsyncCallCounter });
            }
        }, 2000);
    });

    doAsync(true)
        .then(() => doAsync(true))
        .then(() => doAsync(false))
        .then(() => doAsync(true))
        .then(() => doAsync(true))
        .catch(err => {
            console.log(err);
        })

</script>

{% endhighlight %}

<br/>

### Grouping Promises

<br/>

{% highlight javascript linenos %}

<script>

    'use strict';

    let doAsyncCallCounter = 0;

    const doAsync = doesResolve => new Promise((resolve, reject) => {


    });

    setTimeout( () => {
        console.log('a');
    }, 2000);


    setTimeout( () => {
        console.log('b');
    }, 1000);

    setTimeout( () => {
        console.log('c');
    }, 3000);

    const allDone = () => {
        console.log('all done');
    }

</script>

{% endhighlight %}

<br/>

{% highlight javascript linenos %}

<script>

    'use strict';

    let doAsyncCallCounter = 0;

    const doAsync = doesResolve => new Promise((resolve, reject) => {


    });

    let cbCounter = 0;

    cbCounter++;
    setTimeout( () => {
        console.log('a');
        cbCounter--;
        if (cbCounter === 0){
            allDone();
        }
    }, 2000);

    cbCounter++;
    setTimeout( () => {
        console.log('b');
        cbCounter--;
        if (cbCounter === 0){
            allDone();
        }
    }, 1000);

    cbCounter++;
    setTimeout( () => {
        console.log('c');
        cbCounter--;
        if (cbCounter === 0){
            allDone();
        }
    }, 3000);

    const allDone = () => {
        console.log('all done');
    }

</script>

{% endhighlight %}

<br/>

{% highlight javascript linenos %}

<script>

    'use strict';

    let doAsyncCallCounter = 0;

    const doAsync = (doesResolve, timeout) => new Promise((resolve, reject) => {

        let currentCounterValue = ++doAsyncCallCounter;

        setTimeout ( () => {

            if (doesResolve){
                console.log('success!', currentCounterValue);
                resolve({ msg: 'success!', counter: currentCounterValue});
            } else {
                console.log('failure!', currentCounterValue);
                resolve({ msg: 'failure!', counter: currentCounterValue});
            }

        }, timeout);
    });

    const p1 = doAsync(true, 2000);
    const p2 = doAsync(true, 1000);
    const p3 = doAsync(true, 3000);

    Promise.all([p1,p2,p3]).then(results => {
        console.log('all done');
        console.log(results);
    }).catch( results => {
        console.log('one failed');
        console.log(results);
    });

</script>

{% endhighlight %}

<br/>

### Promise Racing

<br/>

{% highlight javascript linenos %}

<script>

    'use strict';

    let doAsyncCallCounter = 0;

    const doAsync = (doesResolve, timeout) => new Promise((resolve, reject) => {

        let currentCounterValue = ++doAsyncCallCounter;

        setTimeout ( () => {

            if (doesResolve){
                console.log('success!', currentCounterValue);
                resolve({ msg: 'success!', counter: currentCounterValue});
            } else {
                console.log('failure!', currentCounterValue);
                resolve({ msg: 'failure!', counter: currentCounterValue});
            }

        }, timeout);
    });

    Promise.race( [ doAsync(true, 2000), doAsync(true, 1000) ] )
        .then( results => {
            console.log('race is over');
            console.log(results);
        });

</script>

{% endhighlight %}
