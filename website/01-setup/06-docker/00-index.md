---
layout: page
title: Docker
description: Docker
keywords: docker, containers
permalink: /setup/docker/
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

### [Environment example for development JS Apps Inside Docker](https://github.com/wildmakaka/Rolling-Scopes-School-Nodejs-Course-Task-6-Docker-basics)

### [React](/setup/docker/react/)

### [DataBases](/setup/docker/db/)

### [Awesome Compose](https://github.com/docker/awesome-compose)

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

https://www.youtube.com/watch?v=1N6VBHMoPsw
