---
layout: page
title: Docker MySQL DataBase
description: Docker MySQL DataBase
keywords: env, docker, database, mysql
permalink: /env/docker/db/mysql/
---

<br/>

# Docker MySQL DataBase

<br/>

    $ vi docker-compose.yml

<br/>

```yaml
version: '3'
services:
  mysql-dev:
    restart: always
    image: mysql
    volumes:
      - ./mysql:/etc/mysql/conf.d
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: databasename
```

<br/>

```
$ docker-compose up
```
