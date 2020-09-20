---
layout: page
title: Run local kubernetes cluster
description: Run local kubernetes cluster
keywords: Run local kubernetes cluster
permalink: /containers/kubernetes/install/
---

# Run local kubernetes cluster

VirtualBox, Vagrant should be installed. It is simple.

<br/>

### Install kubectl (client to work with kubernetes cluster)

<br/>

```shell

-- get current stable version (v1.14.1)
$ echo $(curl -sS https://storage.googleapis.com/kubernetes-release/release/stable.txt)


-- install
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/

```

<br/>

### Prepare hosts file

<br/>

    $ sudo vi /etc/hosts

```
#---------------------------------------------------------------------
# Kubernetes cluster
#---------------------------------------------------------------------

192.168.0.10 master.k8s master
192.168.0.11 node1.k8s node1
192.168.0.12 node2.k8s node2
```

<br/>

### Run local kubernetes cluster

    $ vagrant plugin install vagrant-hostmanager

<br/>

    $ mkdir ~/vagrant-kubernetes && cd ~/vagrant-kubernetes

    # git clone https://bitbucket.org/sysadm-ru/kubernetes .

    $ cd vagrant-provisioning/

    $ vagrant up

<br/>

### Copy special config file on host to manage cluster remotely

<br/>

    $ mkdir -p ~/.kube/config

<br/>

    // root password: kubeadmin
    $ scp root@master:/etc/kubernetes/admin.conf ~/.kube/config

<br/>

    $ kubectl version --short
    Client Version: v1.14.1
    Server Version: v1.14.1

<br/>

    $ kubectl get nodes
    NAME         STATUS   ROLES    AGE     VERSION
    master.k8s   Ready    master   14m     v1.14.1
    node1.k8s    Ready    <none>   11m     v1.14.1
    node2.k8s    Ready    <none>   9m34s   v1.14.1
