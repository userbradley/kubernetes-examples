---
title: Metadata
---

```yaml hl_lines="3"
apiVersion: apps/v1
kind: Deployment
metadata:
```

---

### Name

Gives the Deployment a name

```yaml hl_lines="4"
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
```

### Namespace

The namespace the Deployment should go to


```yaml hl_lines="5"
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
  namespace: default
```

### Labels

User readable key/value pairs attached to Deployments

```yaml hl_lines="6"
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

??? "Top tip"
    Labels can be used to organize and to select subsets of objects. Labels can be attached to objects at creation time and subsequently added and modified at any time. Each object can have a set of key/value labels defined. Each Key must be unique for a given object.


### Annotations


Key value pairs added to the deployment.

```yaml hl_lines="4"
apiVersion: apps/v1
kind: Deployment
metadata:
  annotations:
    imageregistry: "https://hub.docker.com/"
    bradley: "is cool"


```

You can use Kubernetes annotations to attach arbitrary non-identifying metadata to objects. Clients such as tools and libraries can retrieve this metadata.


<!-- 

@todo: come back to this later
??? note "New version based on file updates [HELM]"
    This wo
    ```yaml
      template:
        metadata:
          annotations:
            checksum/config: {{ include (print $.Template.BasePath "/configmap.yaml") . | sha256sum }}
            checksum/secret: {{ include (print $.Template.BasePath "/secret.yaml") . | sha256sum }}
    ```

-->