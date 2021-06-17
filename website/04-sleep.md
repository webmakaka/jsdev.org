---
layout: page
title: Sleep
description: Sleep
keywords: Sleep, TimeOut, Example
permalink: /sleep/
---

<br/>

# Sleep

```
await this.sleep();
```

<br/>

```
  sleep() {
    return new Promise<void>((resolve, reject) => {
      setTimeout(() => {
        resolve();
      }, 1000);
    });
  }
```
