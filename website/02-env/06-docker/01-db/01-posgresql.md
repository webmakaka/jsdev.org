---
layout: page
title: Docker PostgreSQL DataBase
description: Docker PostgreSQL DataBase
keywords: env, docker, database, postgresql
permalink: /env/docker/db/postgresql/
---

# Docker PostgreSQL DataBase

<br/>

**.env**

```
DATABASE_HOST=localhost
DATABASE_NAME=db
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
    image: postgres:13-alpine
    restart: always
    container_name: postgres
    hostname: postgres
    ports:
      - ${DATABASE_PORT}:${DATABASE_PORT}
    environment:
      POSTGRES_DB: ${DATABASE_NAME}
      POSTGRES_USER: ${DATABASE_USER}
      POSTGRES_PASSWORD: ${DATABASE_PASSWORD}
      DATABASE_PORT: ${DATABASE_PORT}
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
