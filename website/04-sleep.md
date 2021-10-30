---
layout: page
title: Sleep
description: Sleep
keywords: Sleep, TimeOut, Example
permalink: /sleep/
---

<br/>

# Sleep

```js
await this.sleep();
```

<br/>

```js
  sleep() {
    return new Promise<void>((resolve, reject) => {
      setTimeout(() => {
        resolve();
      }, 1000);
    });
  }
```
