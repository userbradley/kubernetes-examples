---
title: "Deployment"
---

## What is a `deployment`

A Deployment provides declarative updates for Pods and ReplicaSets.

You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired 
state at a controlled rate. You can define Deployments to create new ReplicaSets, or to remove existing Deployments and adopt all their resources with new Deployments.

## Deployment Details 

## API version

```yaml
apps/v1
```

## Kind

```yaml
Deployment
```

---


## Fields


### Metadata

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
```



#### Name

Gives the Deployment a name

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
```

#### Namespace

The namespace the Deployment should go to


```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
  namespace: default
```

#### Labels

User readable key/value pairs attached to Deployments

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
  namespace: default
  labels:
    environment: production
    app: nginx
```

These are entirely human-readable, and do not affect the deployment programmatically. 

> Labels can be used to organize and to select subsets of objects. Labels can be attached to objects at creation time and subsequently added and modified at any time. Each object can have a set of key/value labels defined. Each Key must be unique for a given object.


#### Annotations

Key value pairs added to the deployment. 

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
  namespace: default
  labels:
    environment: production
    app: nginx
  annotations:
    imageregistry: "https://hub.docker.com/"
    bradley: "is cool"


```

You can use Kubernetes annotations to attach arbitrary non-identifying metadata to objects. Clients such as tools and libraries can retrieve this metadata.
Usually used in helm charts to force a new update when a config map is changed

??? note "New version based on file updates"
    ```yaml
      template:
        metadata:
          annotations:
            checksum/config: {{ include (print $.Template.BasePath "/configmap.yaml") . | sha256sum }}
            checksum/secret: {{ include (print $.Template.BasePath "/secret.yaml") . | sha256sum }}
    ```



---






