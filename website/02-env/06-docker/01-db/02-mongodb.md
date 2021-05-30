---
layout: page
title: Docker MongoDB DataBase
description: Docker MongoDB DataBase
keywords: env, docker, database, mongodb
permalink: /env/docker/db/mongodb/
---

<br/>

# Docker MongoDB DataBase

<br/>

    $ vi docker-compose.yml

<br/>

```yaml
version: '3'
services:
  mongodb-dev:
    image: mongo
    restart: always
    ports:
      - '27017:27017'
    environment:
      MONGODB_DATABASE: mongo-database
```

<br/>

    $ docker-compose up

<br/>

**Example:**
https://github.com/webmakaka/NestJS-Fundamentals-Course/blob/main/app/api-mongodb/docker-compose.yml
