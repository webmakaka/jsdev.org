---
layout: page
title: Kubernetes
description: Kubernetes
keywords: kubernetes, postgres
permalink: /env/kubernetes/db/postgres/
---

# Kubernetes

<br/>

**Final:**  
https://github.com/webmakaka/Machine-Learning-on-Kubernetes/tree/master/Chapter04/postgresdb

<br/>

### Creating a ConfigMap to Store Database Details

<br/>

```
$ vi postgres-configmap.yaml
```

<br/>

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: postgres-secret
  labels:
    app: postgres
data:
  POSTGRES_DB: postgresdb
  POSTGRES_USER: admin1
  POSTGRES_PASSWORD: pA55w0rd123
```

<br/>

```
$ kubectl apply -f postgres-configmap.yaml -n keycloak
```

<br/>

### Creating PersistentVolume (PV) and PersistentVolumeClaim (PVC)

<br/>

```
$ vi postgres-volume.yaml
```

<br/>

```yaml
apiVersion: v1
kind: PersistentVolume # Create PV
metadata:
  name: postgres-volume # Sets PV name
  labels:
    type: local # Sets PV's type
    app: postgres
spec:
  storageClassName: manual
  capacity:
    storage: 10Gi # Sets PV's size
  accessModes:
    - ReadWriteMany
  hostPath:
    path: '/data/postgresql' # Sets PV's host path
```

<br/>

```
$ kubectl apply -f postgres-volume.yaml -n keycloak
```

<br/>

```
$ vi postgres-pvc.yaml
```

<br/>

```yaml
apiVersion: v1
kind: PersistentVolumeClaim # Create PVC
metadata:
  name: postgres-volume-claim # Sets PVC's name
  labels:
    app: postgres # Defines app to create PVC for
spec:
  storageClassName: manual
  accessModes:
    - ReadWriteMany
  resources:
    requests:
      storage: 10Gi # Sets PVC's size
```

<br/>

```
$ kubectl apply -f postgres-pvc.yaml -n keycloak
```

<br/>

```
# Get list of PersistentVolume
$ kubectl get pv

# Get list of PersistentVolumeClaim
$ kubectl get pvc -n keycloak
```

<br/>
 
### Creating PostgreSQL Deployment

<br/>

```
$ vi postgres-deployment.yaml
```

<br/>

```yaml
apiVersion: apps/v1
kind: Deployment # Create a deployment
metadata:
  name: postgres # Set the name of the deployment
spec:
  replicas: 3 # Set 3 deployment replicas
  selector:
    matchLabels:
      app: postgres
  template:
    metadata:
      labels:
        app: postgres
    spec:
      containers:
        - name: postgres
          image: postgres:12.10 # Docker image
          imagePullPolicy: 'IfNotPresent'
          ports:
            - containerPort: 5432 # Exposing the container port 5432 for PostgreSQL client connections.
          envFrom:
            - configMapRef:
                name: postgres-secret # Using the ConfigMap postgres-secret
          volumeMounts:
            - mountPath: /var/lib/postgresql/data
              name: postgresdata
      volumes:
        - name: postgresdata
          persistentVolumeClaim:
            claimName: postgres-volume-claim
```

<br/>

```
$ kubectl apply -f postgres-deployment.yaml -n keycloak
```

<br/>

```
// checking Kubernetes deployment
$ kubectl get deployments -n keycloak

// checking pods
$ kubectl get pods -n keycloak
```

<br/>

### Creating a Service for PostgreSQL

<br/>

```
$ vi postgres-service.yaml
```

<br/>

```yaml
apiVersion: v1
kind: Service # Create service
metadata:
  name: postgres # Sets the service name
  labels:
    app: postgres # Defines app to create service for
spec:
  type: NodePort # Sets the service type
  ports:
    - port: 5432 # Sets the port to run the postgres application
  selector:
    app: postgres
```

<br/>

```
$ kubectl apply -f postgres-service.yaml -n keycloak
```

<br/>

```
$ kubectl get svc -n keycloak
```

<br/>

### Connecting to PostgreSQL via kubectl Command

<br/>

```
$ kubectl exec -it postgres-9db8ff595-55m9j -n keycloak -- psql -h localhost -U admin1 --password -p 5432 postgresdb
```

<br/>

```
postgresdb=# \conninfo
You are connected to database "postgresdb" as user "admin1" on host "localhost" (address "127.0.0.1") at port "5432".
```

<br/>

### Connecting to PostgreSQL via PostgreSQL Client

<br/>

```
$ kubectl get svc -n keycloak
NAME       TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
keycloak   ClusterIP   10.98.138.21    <none>        8080/TCP         47m
postgres   NodePort    10.103.47.237   <none>        5432:31448/TCP   5m59s
```

<br/>

```
$ psql -h 192.168.49.2 -U admin1 --password -p 31448 postgresdb
```

<br/>

```
$ minikube ip --profile ${PROFILE}
```

<br/>

```
postgresdb=# \conninfo
You are connected to database "postgresdb" as user "admin1" on host "192.168.49.2" at port "31448".
```

<br/>

**Thansk to:**  
https://adamtheautomator.com/postgres-to-kubernetes/
