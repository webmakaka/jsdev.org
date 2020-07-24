---
layout: page
title: Running a Node.js Container on Google Kubernetes Engine
permalink: /clouds/google/kubernetes/running-nodejs-container-on-gke/
---

# [GSP015] Running a Node.js Container on Google Kubernetes Engine


https://www.qwiklabs.com/focuses/5982?catalog_rank=%7B%22rank%22%3A4%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=2790268

<br/>

You can find coupons for labs  <a href="https://medium.com/@sathishvj/qwiklabs-free-codes-gcp-and-aws-e40f3855ffdb" rel="nofollow">here</a>. I didn't pay money for this. Because i am poor. 

<br/>

### Overview

Google Kubernetes Engine makes it easy to run Docker containers in the cloud. Google Kubernetes Engine uses Kubernetes, an open source container scheduler, to ensure that your cluster is running exactly the way you want it to at all times.

In this lab you will learn how to launch a container and how to launch replicas of that container on Google Kubernetes Engine.

<br/>

### Creating a Cluster

    $ gcloud config set compute/zone us-central1-a
    $ gcloud container clusters create hello-world

<br/>

### Building and Publishing the Node.js App

    $ echo $DEVSHELL_PROJECT_ID

    $ git clone https://github.com/GoogleCloudPlatform/nodejs-docs-samples.git

    $ cd nodejs-docs-samples/containerengine/hello-world/

<br/>

    $ cat Dockerfile

```
FROM node:6-alpine
EXPOSE 8080
COPY server.js .
CMD node server.js
```

    $ docker build -t gcr.io/$DEVSHELL_PROJECT_ID/hello-node:1.0 .

    // Publish the container
    $ gcloud docker -- push gcr.io/$DEVSHELL_PROJECT_ID/hello-node:1.0


<br/>

### Deploying the Node.js App

    $ kubectl run hello-node --image=gcr.io/$DEVSHELL_PROJECT_ID/hello-node:1.0 --port=8080

    $ kubectl get deployments

    $ kubectl get pods

    // Allow External Traffic
    $ kubectl expose deployment hello-node --name=hello-node --type=LoadBalancer --port=80 --target-port=8080

    $ kubectl get svc hello-node
    NAME         TYPE           CLUSTER-IP    EXTERNAL-IP      PORT(S)        AGE
    hello-node   LoadBalancer   10.0.10.239   35.192.224.241   80:30099/TCP   88s


http://35.192.224.241/
OK