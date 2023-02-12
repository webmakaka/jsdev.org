---
layout: page
title: Logging ELK Elasticsearch, Logstash, and Kibana
description: Logging ELK Elasticsearch, Logstash, and Kibana
keywords: logging, ELK, Elasticsearch, Logstash, Kibana
permalink: /logging/elk/
---

# Logging

<br/>

### Logging Nodejs apps with ELK: Elasticsearch, Logstash, and Kibana

<br/>

**Inside morgan, winston**

<br/>

https://www.youtube.com/watch?v=nnpcTyHZvS8

https://github.com/rekibnikufesin/nodejs-logging-elk

<br/>

### How to run

```
$ docker-compose up
```

<br/>

**Possible need to update **

```
  "scripts": {
    "start": "node ./bin/www",
    "dev": "npm run migrate && npm run seed && nodemon --inspect=0.0.0.0:9229 ./bin/www",
    "migrate": "knex migrate:latest",
    "seed": "knex seed:run"
  },
```

<br/>

**Should works**

```
http://localhost:3000/

F5 F5 F5 F5 F5


// Possible can kill app if will not receive data
http://localhost:3000/users
```

<br/>

```
// Restart container with application
$ docker stop expressjs && docker start expressjs
```

<br/>

```
// Check indices
http://localhost:9200/_cat/indices
```

**Kibana**  
http://localhost:5601/

<br/>

```
Kibana -> Index Patterns -> "logstash-2021.07.06-000001" -> Next
```

<br/>

```
I don't want to user the Time Filter
```

Create index pattern

<br/>

Kibana -> Discover
