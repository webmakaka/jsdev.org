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
    ports:
      - '3306:3306'
    volumes:
      - ./mysql:/etc/mysql/conf.d
    environment:
      MYSQL_DATABASE: databasename
      MYSQL_ROOT_PASSWORD: p@55w0rd1
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
$ mysql --user=root --password=p@55w0rd1 -h 127.0.0.1 databasename
```

<br/>

```
mysql> SELECT DATABASE();
```
