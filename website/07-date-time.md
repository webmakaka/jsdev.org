---
layout: page
title: Date Time
description: Date Time
keywords: Date Time
permalink: /date-time/
---

<br/>

# Date Time

<br/>

### date-fns

```
$ yarn add date-fns
```

<br/>

**Example 1**

```js
import { format } from 'date-fns';

***

MyWebsite 2020 - {format(new Date(), 'yyyy')} All rights reserved.

```

<br/>

**Example 2**

```js
import { format } from 'date-fns';
import { ru } from 'date-fns/locale';

***

{format(new Date(createdAt), 'dd MMMM yyyy', { locale: ru })}

```

<br/>

### Moment
