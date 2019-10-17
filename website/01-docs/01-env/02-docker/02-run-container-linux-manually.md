---
layout: page
title: Create Docker Container from Dockerfile
permalink: /env/docker/run-container/linux/manually/
---

# Create Docker Container from Dockerfile


    $ docker pull node
    
<br/>
    
    $ docker image ls | grep node

<br/>

    $ mkdir -p ~/dockerfiles
    $ cd ~/dockerfiles

<br/>

    $ vi nodejs.dockerfile

<br/>

{% highlight shell linenos %}

FROM node:latest

RUN apt-get update && apt-get install -qq -y vim git curl net-tools

ENV PROJECT_PATH /project
RUN mkdir -p $PROJECT_PATH
RUN mkdir -p /usr/local/lib/node_modules/
RUN npm install -g npm@latest nodemon@latest

WORKDIR $PROJECT_PATH


USER root
CMD ["bash"]

{% endhighlight %}


<br/>

    $ docker build -f nodejs.dockerfile -t marley/nodejs .
    
<br/>
    
    $ docker image ls | grep marley/nodejs
    marley/nodejs               latest              798c422b32ac        41 seconds ago      717MB
