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

```
$ vi docker-compose.yml
```

<br/>

```yaml
version: '3'
services:
  mysql-dev:
    restart: always
    image: mysql:8.1
    ports:
      - '3306:3306'
    volumes:
      - ./mysql:/etc/mysql/conf.d
    environment:
      MYSQL_DATABASE: db
      MYSQL_ROOT_PASSWORD: pA55w0rd123
```

<br/>

```
$ docker-compose up
```

<br/>

```
$ telnet localhost 3306
```

<br/>

```
$ sudo apt update -y
$ sudo apt install -y mysql-client
```

<br/>

```
$ mysql --user=root --password=pA55w0rd123 -h 127.0.0.1 db
```

<br/>

```
mysql> SELECT DATABASE();
```
