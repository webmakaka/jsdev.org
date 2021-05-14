---
layout: page
title: Docker PostgreSQL DataBase
description: Docker PostgreSQL DataBase
keywords: env, docker, database, postgresql
permalink: /env/docker/db/postgresql/
---

<br/>

# Docker PostgreSQL DataBase

<br/>

    $ vi docker-compose.yml

<br/>

```yaml
version: '3'
services:
  db:
    image: postgres
    restart: always
    ports:
      - '5432:5432'
    environment:
      POSTGRES_PASSWORD: pass123
```

<br/>

**.env**

```
DATABASE_HOST=localhost
DATABASE_NAME=postgres
DATABASE_PORT=5432
DATABASE_USER=postgres
DATABASE_PASSWORD=pass123
SECRET_KEY=1HyftmH8tPzutU46s2MXM87QuF844WKm
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
