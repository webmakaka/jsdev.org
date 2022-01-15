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
DATABASE_USER=user1
DATABASE_PASSWORD=pA55w0rd123
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
    image: postgres:14.1-alpine3.15
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

**Import data into postgresql from sql dump file**

```
$ cd data/

// pass pA55w0rd123
$ psql -U user1 -h localhost -p 5432 -d go_movies < go_movies.sql
```

<br/>

```
$ PGPASSWORD=pA55w0rd123 psql --host=localhost --username=user1 --port=5432 --dbname=go_movies -c 'select id, title, description, year, release_date, rating, runtime, mpaa_rating, created_at, updated_at from movies where id = 1'
```

<br/>

```
$ PGPASSWORD=pA55w0rd123 psql --host=localhost --username=user1 --port=5432 --dbname=go_movies -c "INSERT INTO movies_genres (movie_id, genre_id, created_at, updated_at) VALUES (1, 1, '2021-05-19', '2021-05-19');"
```

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
