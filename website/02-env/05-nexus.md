---
layout: page
title: Nexus
description: Nexus
keywords: nexus, hosted, nodejs, npm
permalink: /env/nexus/
---

# Nexus Local Repo (hosted)

<br/>

npm (hosted)

<br/>

name: npm-internal

<br/>

```
$ npm pack --dry-run lodash
$ npm pack lodash
```

<br/>

```
// Possible not needed
$ npm login --registry=https://192.168.1.9:8080/repository/npm-internal/
```

<br/>

```
$ npm config set strict-ssl false
```

<br/>

```
$ npm config list
```

<br/>

```
$ echo -n 'admin:admin123' | openssl base64
YWRtaW46YWRtaW4xMjM=
```

<br/>

```
$ vi ~/.npmrc
```

<br/>

```
strict-ssl=false
email=marley@example.com
always-auth=true
_auth=YWRtaW46YWRtaW4xMjM=
```

<br/>

```
$ npm publish lodash-4.17.21.tgz --registry=https://192.168.1.9:8080/repository/npm-internal/
```

<br/>

```
$ npm init -y
$ npm install lodash --registry=https://192.168.1.9:8080/repository/npm-internal/
```

<br/>

**Materials:**

https://help.sonatype.com/repomanager2/node-packaged-modules-and-npm-registries#NodePackagedModulesandnpmRegistries-EncodingCredentialsonLinux

https://levelup.gitconnected.com/deploying-private-npm-packages-to-nexus-a16722cc8166
