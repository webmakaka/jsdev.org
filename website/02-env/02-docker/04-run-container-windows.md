---
layout: page
title: Run Docker Container (with node.js) in Windows 10
description: Run Docker Container (with node.js) in Windows 10
keywords: Run Docker Container (with node.js) in Windows 10
permalink: /env/docker/run-container/windows/
---

# Run Docker Container (with node.js) in Windows 10 (Docker Quick Start Terminal)

<br/>

Prepared containers with node:  
https://hub.docker.com/_/node/

<br/>

Prepared scripts for create Docker container:  
https://github.com/nodejs/docker-node/

<!-- $ curl -L -o Dockerfile https://github.com/nodejs/docker-node/blob/master/7.4/Dockerfile?raw=true -->

<br/>

### Step1: download prepared container

    $ docker pull node

<br/>

### Docker and Network in Windows

    $ docker-machine env default
    $ eval $("C:\Program Files\Docker Toolbox\docker-machine.exe" env default)

<br/>

    $ docker-machine ip
    192.168.99.100

<br/>

    $ docker-machine ls
    NAME      ACTIVE   DRIVER       STATE     URL                         SWARM   DOCKER    ERRORS
    default   -        virtualbox   Running   tcp://192.168.99.100:2376           v1.11.0

<br/>

    $ docker-machine status default
    Running

<br/>

And with this container you can work by IP 192.168.99.100

<br/>

### Step 3: Create and Run Docker Container

    $ project_name=<my_project_name>

<br/>

    $ echo ${project_name}

    $ mkdir -p ~/projects/dev/${project_name}

<br/>

    $ cd ~/projects/dev/${project_name}

<br/>

    // For Example:
    $ git clone https://bitbucket.org/marley-react/The-Complete-React-Web-App-Developer-Course .

and now you can work with this project with any editor.

<br/>

```
$ docker run -it \
-p 80:8080 -p 1337:1337 -p 3000:3000 -p 4000:4000 -p 5000:5000 -p 6000:6000 -p 7000:7000 -p 8000:8000 -p 9000:9000 \
--name ${project_name} \
-v ~/projects/dev/${project_name}:/project \
node \
/bin/bash
```

<br/>

    # node -v
    v7.4.0

<br/>

    # npm -v
    4.0.5

<br/>

    # apt-get -qq update

    # apt-get install -y vim curl net-tools

net-tools contains ifconfig

**create user without additional questions:**

    # adduser --disabled-password --gecos "" developer

    # su - developer
    $ cd /project/

<br/>

And as result, we can work with project on local computer and run project in docker container.
In docker container project locate in /project folder.

If you start app, you can connect:
http://192.168.99.100:3000/

<br/>

### npm ERR! EPROTO: protocol error, symlink '../mime/cli.js' -> '/project/node_modules/.bin/mime'

Use next command:

    $ npm install express --no-bin-links
