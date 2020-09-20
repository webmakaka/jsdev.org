---
layout: page
title: Deploy Node.js Express Application in App Engine
description: Deploy Node.js Express Application in App Engine
keywords: Deploy Node.js Express Application in App Engine
permalink: /clouds/google/gae/
---

# [GSP028] Deploy Node.js Express Application in App Engine

https://google.qwiklabs.com/focuses/3340?parent=catalog&qlcampaign=1q-clouddev-009

<br/>

You can find coupons for labs <a href="https://medium.com/@sathishvj/qwiklabs-free-codes-gcp-and-aws-e40f3855ffdb" rel="nofollow">here</a>. I didn't pay money for this. Because i am poor.

<br/>

### Overview

Google App Engine applications are easy to create, easy to maintain, and easy to scale as your traffic and data storage needs change. With App Engine, there are no servers to maintain. You simply upload your application and it's ready to go.

App Engine applications automatically scale based on incoming traffic. load balancing, microservices, authorization, SQL and NoSQL databases, Memcache, traffic splitting, logging, search, versioning, roll out and roll backs, and security scanning are all supported natively and are highly customizable.

App Engine's environments, the Standard Environment and the Flexible environment, support a host of programming languages, including Java, Python, PHP, Node.js, Go, etc.. The two environments give users maximum flexibility in how their application behaves since each environment has certain strengths. Read The App Engine Environments for more information.

This tutorial uses the sample code from the Google Cloud Node.js Getting Started guide. You will learn how to to connect to computing resources hosted on Google Cloud Platform via the web. You will learn how to use Cloud Shell and the Cloud SDK gcloud command.

What you'll learn

- How to create a Node.js Express application on Google App Engine.
- How to update the code without taking the server down.

<br/>

### Enable the App Engine Admin API

Navigation menu > APIs & services > Dashboard > Enable APIs and services > App Engine Admin API > Enable

<br/>

### Get the Getting Started Example source code

Google shell console

    $ git clone https://github.com/GoogleCloudPlatform/nodejs-docs-samples.git && cd nodejs-docs-samples/appengine/hello-world/flexible

    $ npm install

<br/>

### Run the Application Locally

    $ npm start

Web Preview icon in the Cloud Shell toolbar and choose preview on port 8080.

    $  Ctrl + C

<br/>

### Deploying the Application into App Engine

App Engine uses a file called app.yaml to describe an application's deployment configuration. If this file is not present, App Engine will try to guess the deployment configuration. However, it is a good idea to provide this file.

    $ cat app.yaml

```
runtime: nodejs
env: flex

manual_scaling:
  instances: 1
resources:
  cpu: 1
  memory_gb: 0.5
  disk_size_gb: 10

```

<br/>

    $ gcloud app deploy

Because this is the first time you are deploying App Engine, the tool will prompt you to select a location to deploy the app. For this lab choose us-central.

After the application deploys, you can visit it by opening the URL http://<project-id>.appspot.com in your web browser. The project-id is the GCP Project ID in the CONNECTION DETAILS section of the lab.

<br/>

https://qwiklabs-gcp-cae14acd7feed21e.appspot.com

<br/>

### Updating the Application

Update the application to generate a UUID every time someone visits the page.

Install the uuid package with npm:

    $ npm install uuid --save

    $ vi app.js

Add the following in app.js file:

```
const uuid = require('uuid');

***

res.status(200).send(`Hello, ${uuid()}!`);
```

    $ gcloud app deploy
