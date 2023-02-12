---
layout: page
title: Docker installation in Ubuntu
description: Docker installation in Ubuntu
keywords: Docker installation in Ubuntu
permalink: /devops/containers/docker/setup/
---

# Docker installation in Ubuntu

<br/>

works in 18, 20

```
$ mkdir ~/tmp
$ cd ~/tmp
$ vi install-docker-and-docker-compose.sh

```

<br/>

```
# Install Docker

sudo apt-get update
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install -y docker-ce


# Install Docker-Compose

LATEST_VERSION=$(curl --silent "https://api.github.com/repos/docker/compose/releases/latest" | grep '"tag_name"' | sed -E 's/.*"([^"]+)".*/\1/')

sudo curl -L "https://github.com/docker/compose/releases/download/${LATEST_VERSION}/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

<br/>

    $ chmod +x ./install-docker-and-docker-compose.sh
    $ sudo ./install-docker-and-docker-compose.sh

<br/>

```
$ docker -v
Docker version 19.03.12, build 48a66213fe

$ docker-compose --version
docker-compose version 1.27.2, build 18f557f9
```

<br/>

### Add the user who will work with docker

    # usermod -aG docker <username>

<br/>

reboot
