---
layout: page
title: Dockerfiles for React.js apps
permalink: /client/react/dockerfiles/
---

# Dockerfiles for React.js apps

<br/>

### Develpment

**Dockerfile.dev**

```bash
FROM node:alpine

RUN apk update && apk upgrade && \
    apk add --no-cache bash git vim

WORKDIR '/project'

COPY ./package*.json .
RUN npm install

COPY . .

CMD ["npm", "run", "start"]

```

    $ docker build -t marley/docker-react -f Dockerfile.dev .

    $ docker run -p 3000:3000 marley/docker-react

or

    $ docker run -p 3000:3000 -v /project/node_modules -v $(pwd):/project marley/docker-react

or

    $ docker run -it -p 3000:3000 -v /project/node_modules -v $(pwd):/project marley/docker-react bash

<!--

$ docker run -p 3000:3000 -v /project/node_modules -v $(pwd):/project <image_id>


docker-compose.yml

version: '3'
services:
  react-app:
    web:
      build:
        context: .
        dockerfile: Dockerfile.dev
      ports:
        - "3000:3000"
      volumes:
        - /project/node_modules
        - .:/project


$ docker-compose up

-->

<br/>

### Tests

    $ docker run -it <image_id> npm run test

<!--

version: '3'
services:
  react-app:
    web:
      build:
        context: .
        dockerfile: Dockerfile.dev
      ports:
        - "3000:3000"
      volumes:
        - /project/node_modules
        - .:/project
    tests:
      build:
        context: .
        dockerfile: Dockerfile.dev
      volumes:
        - /project/node_modules
        - .:/project
      command: ["npm", "run", "test"]



docker-compose up --build

docker attach

-->

<br/>

### Production

**Dockerfile**

```
FROM node:alpine as builder
WORKDIR '/project'

COPY ./package.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx
COPY --from=builder /project/build /usr/share/nginx/html
```

    $ docker build .
    $ docker run -p 8080:80 <image_id>

<br/>

From video course

[Stephen Grider] Docker and Kubernetes: The Complete Guide [ENG, 2018]
