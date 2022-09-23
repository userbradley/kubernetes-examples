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
metadata:
  name: hello-v3
```

#### Namespace

The namespace the Deployment should go to

```yaml
metadata:
  name: hello-v3
  namespace: default
```

#### Labels

User readable key/value pairs attached to Deployments

```yaml
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

Allows you to add annotations to the Deployment

---




