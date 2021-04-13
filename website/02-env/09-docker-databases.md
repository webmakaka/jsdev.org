---
layout: page
title: Docker DataBases
description: Docker DataBases
keywords: env, docker, database, postgresql, mongodb
permalink: /env/docker-databases/
---

<br/>

# Docker DataBases

<br/>

### PostgreSQL

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

**Example:**  
https://github.com/webmakaka/Uber-Eats-Clone

<br/>

<br/>

Run pgadmin in docker container:

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

### MongoDB

```yaml
version: '3'
services:
  db:
    image: mongo
    restart: always
    ports:
      - '27017:27017'
    environment:
      MONGODB_DATABASE: mongo-database
```

<br/>

**Example:**
https://github.com/webmakaka/NestJS-Fundamentals-Course/

<br/>

### docker-db-templates

https://github.com/dalisoft/dev-env/tree/master/packages/docker-db-templates
