---
layout: page
title: Docker
permalink: /env/docker/
---

# Docker

<br/>

### Run Docker Container:

[Run Docker Container (with node.js) in Linux](/env/docker/run-container/linux/)  

[Run Docker Container (with node.js) in Windows 10](/env/docker/run-container/windows/)  


<br/>

### Most Important Docker Commands After Container Has Been Created

    // show running containers
    $ docker ps

    // show all containers
    $ docker ps -a

    $ docker start <container_name>
    $ docker attach <container_name>

    // connect to docker container by additional terminal
    $ docker exec -it <container_name> bash

    // detach from container without stopping
    CTRL + P + Q



<br/>

### Some examples


A sample todo app with React and Flux in ES2015 (ES6) served by Hapi  
https://github.com/tribou/react-todo
