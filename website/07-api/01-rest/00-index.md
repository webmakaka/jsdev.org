---
layout: page
title: Rest
description: Rest
keywords: api, rest
permalink: /api/rest/
---

# Rest

<br/>

### Create a simple rest API service

<br/>

    $ yarn global add json-server

<br/>

    $ cd app/api
    $ json-server --watch db.json --port 3001

http://localhost:3000/entries/

<br/>

**db.json**

<br/>

```json
{
  "entires": [
    {
      "id": 1,
      "description": "Work income reducer",
      "value": 1000.0,
      "isExpense": false
    },
    {
      "id": 2,
      "description": "Water bill reducer",
      "value": 20.0,
      "isExpense": true
    },
    {
      "id": 3,
      "description": "Rent reducer",
      "value": 300.0,
      "isExpense": true
    },
    {
      "id": 4,
      "description": "Power bill reducer",
      "value": 50.0,
      "isExpense": true
    }
  ]
}
```

<br/>

[Example](https://github.com/webmakaka/React-React-Redux-and-Redux-Saga-Master-React-State-Hooks)

<br/>

### [Application with a good example 1 - JS](https://github.com/webmak1/Rolling-Scopes-School-Nodejs-Course-Task-2-Express-Rest-Service)

<br/>

### [Building Strongly Typed REST Clients with Typescript - Jose Manuel Heredia Hidalgo, Microsoft](https://www.youtube.com/watch?v=xdylpZ3jOGs)
