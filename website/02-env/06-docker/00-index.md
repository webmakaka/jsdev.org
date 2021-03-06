---
layout: page
title: Docker
description: Docker
keywords: docker, containers
permalink: /env/docker/
---

# Docker

<br/>

### Clean everything

```sh
$ {
  docker system prune -a -f
  docker container prune -f
  docker image prune -a -f
  docker volume prune -f
  docker network prune -f
}
```

<br/>

### [Environment example for development JS Apps Inside Docker](https://github.com/webmak1/Rolling-Scopes-School-Nodejs-Course-Task-6-Docker-basics)

### [React](/env/docker/react/)

### [DataBases](/env/docker/db/)

<br/>

### Complete intro to containers

https://btholt.github.io/complete-intro-to-containers/

<br/>

### Test docker containers

```
$ docker scan webmakaka/rsschool-postgres
```

<br/>

https://snyk.io/
