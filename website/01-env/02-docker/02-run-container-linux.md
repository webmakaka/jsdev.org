---
layout: page
title: Run Docker Container (with node.js)
permalink: /env/docker/run-container/linux/
---

# Run Docker Container (with node.js v10.X.X)

Prepared containers with node:  
https://hub.docker.com/_/node/

Prepared scripts for create Docker container:  
https://github.com/nodejs/docker-node/

<!-- $ wget -O Dockerfile https://github.com/nodejs/docker-node/blob/master/7.4/Dockerfile?raw=true    -->

<br/>

### Get prepared docker container

    $ docker pull marley/nodejs

or <a href="/env/docker/run-container/linux/manually/">Create Docker Container from Dockerfile</a>

<br/>

**Prepare Environment for Development**

<br/>

    $ project_name=building-an-angular-application-with-node-and-token
    $ project_folder=~/projects/dev/js/nodejs

<br/>

    $ echo ${project_folder}/${project_name}
    /home/marley/projects/dev/js/nodejs/building-an-angular-application-with-node-and-token

<br/>

    $ mkdir -p ${project_folder}/${project_name}

<br/>

```shell
$ docker run -it \
-p 80:8080 -p 1337:1337 -p 3000:3000 -p 4000:4000 -p 5000:5000 -p 7000:7000 -p 8000:8000 -p 9000:9000 \
--name ${project_name} \
--hostname ${project_name} \
-v ${project_folder}/${project_name}:/project \
marley/nodejs
```

<!-- <br/>

If error

    request to https://registry.npmjs.org/express-messages failed, reason: Hostname/IP doesn't match certificate's altnames: "Host: registry.npmjs.org. is not in the cert's altnames: DNS:a.sni.fastly.net, DNS:a.sni.global-ssl.fastly.net"

<br/>

    $ dig www.npmjs.com @1.1.1.1

<br/>

```shell
$ docker run -it \
-p 80:8080 -p 1337:1337 -p 3000:3000 -p 4000:4000 -p 5000:5000 -p 7000:7000 -p 8000:8000 -p 9000:9000 \
--name ${project_name} \
--hostname ${project_name} \
--dns=1.1.1.1 \
--add-host www.npmjs.com:104.16.110.30 \
--add-host registry.npmjs.org:104.16.110.30 \
-v ${project_folder}/${project_name}:/project \
marley/nodejs
``` -->

<br/>

**Inside container**

<br/>

```shell
# username=nodejs
# adduser --disabled-password --gecos "" ${username}
# usermod -aG sudo ${username}
# chown -R ${username} /project/
# chown -R ${username} /usr/local/lib/node_modules/
# chown -R ${username} /usr/local/bin/
# su - ${username}
```

<br/>

    $ vi ~/.bashrc

<br/>

In the bottom I am add next, to work with .bash_profile like in redhat distrib's

```shell
###############################
# USER DEFINED .bash_profile

source ~/.bash_profile
###############################
```

<br/>

    $ echo "export PS1='$ '" >> ~/.bash_profile
    $ echo 'export PATH=$PATH:./node_modules/.bin' >> ~/.bash_profile

    $ source ~/.bash_profile

<br/>

### Some info

    $ cat /etc/os-release
    PRETTY_NAME="Debian GNU/Linux 8 (jessie)"
    NAME="Debian GNU/Linux"
    VERSION_ID="8"
    VERSION="8 (jessie)"
    ID=debian
    HOME_URL="http://www.debian.org/"
    SUPPORT_URL="http://www.debian.org/support"
    BUG_REPORT_URL="https://bugs.debian.org/"

<br/>

    $ node --version
    v11.3.0

<br/>

    $ npm --version
    6.4.1

<br/>

### Additional info (not so interesting)

    $ node

    > os.type()
    'Linux'

    > os.release()
    '4.4.0-116-generic'

<!--
remove old images
$ docker rmi $(docker images | grep '^<none>' | awk '{print $3}')
-->

<br/>

After all, i can open ${project_folder}/${project_name} in my editor.

<br/>

    $ cd ${project_folder}/${project_name}

<br/>

    $ code .

or

    $ atom .

All content will be also available in /project folder in the container.
And application I will run inside container, and install any packages too.

When i have some permission issue, I am solve it by command:

    # chmod -R 777 ${project_folder}/${project_name}

    # chown -R <username> {project_folder}/${project_name}
