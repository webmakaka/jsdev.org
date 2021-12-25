---
layout: page
title: Docker PostgreSQL DataBase
description: Docker PostgreSQL DataBase
keywords: env, docker, database, postgresql
permalink: /env/docker/db/postgresql/
---

# Docker PostgreSQL DataBase

<br/>

```
$ sudo vi /etc/hosts
```

<br/>

```
127.0.0.1 postgres
```

<br/>

**.env**

```
DATABASE_HOST=postgres
DATABASE_NAME=postgres-db
DATABASE_PORT=5432
DATABASE_USER=user
DATABASE_PASSWORD=pass123
```

<br/>

```
$ vi docker-compose.yml
```

<br/>

```yaml
version: '3'
services:
  postgres:
    container_name: postgres
    image: postgres:14.1-alpine
    restart: always
    hostname: ${DATABASE_HOST}
    ports:
      - ${DATABASE_PORT}:5432
    environment:
      POSTGRES_DB: ${DATABASE_NAME}
      POSTGRES_USER: ${DATABASE_USER}
      POSTGRES_PASSWORD: ${DATABASE_PASSWORD}
    volumes:
      - ./PGDATA:/var/lib/postgresql/data
```

<br/>

    $ docker-compose up

<br/>

**Example:**  
https://github.com/webmakaka/Uber-Eats-Clone

<br/>

### Run pgadmin in docker container:

```
$ docker run -e PGADMIN_DEFAULT_EMAIL='postgres@test.com' -e PGADMIN_DEFAULT_PASSWORD='password1234' -p 5555:80 --name pgadmin dpage/pgadmin4
```

<br/>

http://localhost:5555/

```
login: postgres@test.com
pass: password1234
```

<br/>

To connect, use host ip address
