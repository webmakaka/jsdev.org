---
layout: page
title: Hello Node Kubernetes
permalink: /clouds/google/kubernetes/hello-node-kubernetes/
---

# [GSP005] Hello Node Kubernetes


https://google.qwiklabs.com/focuses/564?catalog_rank=%7B%22rank%22%3A5%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=2790370

<br/>

You can find coupons for labs  <a href="https://medium.com/@sathishvj/qwiklabs-free-codes-gcp-and-aws-e40f3855ffdb" rel="nofollow">here</a>. I didn't pay money for this. Because i am poor. 

<br/>

I will use my own application

<br/>

    $ export PROJECT_ID=$(gcloud config get-value project)
    $ gcloud config set project ${PROJECT_ID}

    $ gcloud container clusters create hello-world \
                --num-nodes 2 \
                --machine-type n1-standard-1 \
                --zone us-central1-a

<br/>

    $ git clone https://github.com/webmakaka/cats-app
    $ cd cats-app

    $ docker build -t gcr.io/${PROJECT_ID}/hello-node:v1 .

    $ docker push gcr.io/${PROJECT_ID}/hello-node:v1

    $ kubectl run hello-node \
    --image=gcr.io/${PROJECT_ID}/hello-node:v1 \
    --port=8080

    $ kubectl expose deployment hello-node --type="LoadBalancer"

    $ kubectl scale deployment hello-node --replicas=4

    $ kubectl get services
    NAME         TYPE           CLUSTER-IP   EXTERNAL-IP     PORT(S)          AGE
    hello-node   LoadBalancer   10.0.11.98   35.232.237.33   8080:31312/TCP   2m23s
    kubernetes   ClusterIP      10.0.0.1     <none>          443/TCP          5m8s

<br/>

http://35.232.237.33:8080/  
OK

<br/>

### Roll out an upgrade to your service

    $ cd ~/cats-app/views/layouts

    $ vi main.html

```
A node.js Voting Game
```

replace to 

```
A node.js Voting Game in GKE
```

<br/>

    $ cd ~/cats-app/

    $ docker build -t gcr.io/${PROJECT_ID}/hello-node:v2 .
    $ docker push gcr.io/${PROJECT_ID}/hello-node:v2

    $ kubectl edit deployment hello-node

Spec > containers > image

replace image version from v1 to v2

<br/>

http://35.232.237.33:8080/  
OK