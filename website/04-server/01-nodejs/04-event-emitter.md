---
layout: page
title: Node.JS EventEmitter
description: Node.JS EventEmitter
keywords: Node.JS EventEmitter
permalink: /server/nodejs/event-emitter/
---

# Node.JS EventEmitter

<br/>

### Example 1

```js
const EventEmitter = require('events');

const emitter = new EventEmitter();

emitter.on('start', (message) => console.log(message));

emitter.emit('start', 'started');

// emitter.removeAllListeners();
```

<br/>

### Example 2

```js
const EventEmitter = require('events');

class Timer extends EventEmitter {
  constructor(total) {
    super();

    this.total = total;
    this.ticks = 0;
  }

  start() {
    this.interval = setInterval(() => this.tick(), 1000);
    this.emit('start');
  }

  tick() {
    this.ticks += 1;

    if (this.ticks <= this.total) {
      this.emit('tick', this.ticks);
    } else {
      this.end();
    }
  }

  end() {
    clearInterval(this.interval);
    this.emit('end');
  }
}

const timer = new Timer(10);

timer.once('start', () => console.log('Start'));
timer.on('tick', (tick) => console.log(tick));
timer.once('end', () => console.log('End'));

timer.start();
```

res:

```
Start
1
2
3
4
5
6
7
8
9
10
End


```

<br/>

### Example 3

**EventEmitter.js**

```js
class EventEmitter {
  constructor() {
    this.events = {};
  }

  on(type, listener) {
    this.events[type] = this.events[type] || [];
    this.events[type].push(listener);
  }

  emit(type, arg) {
    if (this.events[type]) {
      this.events[type].forEach((listener) => listener(arg));
    }
  }
}

module.exports = EventEmitter;
```

<br/>

**app.js**

```js
const EventEmitter = require('./EventEmitter');

class Timer extends EventEmitter {
  constructor(total) {
    super();

    this.total = total;
    this.ticks = 0;
  }

  start() {
    this.interval = setInterval(() => this.tick(), 1000);
    this.emit('start');
  }

  tick() {
    this.ticks += 1;

    if (this.ticks <= this.total) {
      this.emit('tick', this.ticks);
    } else {
      this.end();
    }
  }

  end() {
    clearInterval(this.interval);
    this.emit('end');
  }
}

const timer = new Timer(10);

timer.on('start', () => console.log('Start'));
timer.on('tick', (tick) => console.log(tick));
timer.on('end', () => console.log('End'));

timer.start();
```

res:

```
Start
1
2
3
4
5
6
7
8
9
10
End


```
