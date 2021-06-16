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

```
$ docker-compose up
```

<br/>

**Example:**
https://github.com/webmakaka/NestJS-Fundamentals-Course/blob/main/app/api-mongodb/docker-compose.yml

<br/>

### Another one version

```yaml
version: '3'
services:
  mongo:
    image: mongo:4.4.6
    container_name: mongo
    restart: always
    environment:
      - MONGO_INITDB_ROOT_USERNAME=admin
      - MONGO_INITDB_ROOT_PASSWORD=admin
    ports:
      - 27017:27017
    volumes:
      - ./mongo-data-4.4:/data/db
    command: --wiredTigerCacheSizeGB 1.5
```

<br/>

**.env**

```
MONGO_DATABASE_NAME=admin
MONGO_LOGIN=admin
MONGO_PASSWORD=admin
MONGO_HOST=localhost
MONGO_PORT=27017
```
