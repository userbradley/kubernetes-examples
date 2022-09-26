---
title: "Deployment"
---

## What is a `deployment`

A Deployment provides declarative updates for Pods and ReplicaSets.

You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired 
state at a controlled rate. You can define Deployments to create new ReplicaSets, or to remove existing Deployments and adopt all their resources with new Deployments.

??? note "Example"

    ``` yaml
    apiVersion: apps/v1 # (1)!
    ```

    1.   [API Documentation](#api-version)

    
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
metadata:
```



#### Name

Gives the Deployment a name

```yaml hl_lines="4"
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
```

#### Namespace

The namespace the Deployment should go to


```yaml hl_lines="5"
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-v3
  namespace: default
```

#### Labels

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


#### Annotations


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
---

## Spec


The specification of the pod(s) running

```yaml hl_lines="4"
apiVersion: apps/v1
kind: Deployment
spec:
```


### Replicas

Telling Kubernetes how many replicas of the pod to run

```yaml hl_lines="4"
apiVersion: apps/v1
kind: Deployment
spec:
  replicas: 3
```

### Strategy

Defines how the containers will be managed during an update

```yaml hl_lines="14"
apiVersion: apps/v1
kind: Deployment
spec:
  replicas: 3
  strategy:

```
#### Type

Defines the type of deployment strategy to Use

Available options are:

- [x] `Recreate`
- [x] `RollingUpdate`

---
##### Recreate

```yaml
apiVersion: apps/v1
kind: Deployment
spec:
  replicas: 36
  strategy:
    type: Recreate
```
??? Note
    This will only guarantee Pod termination previous to creation for upgrades. If you upgrade a Deployment, all Pods of the old revision will be terminated immediately. Successful removal is awaited before any Pod of the new revision is created. If you manually delete a Pod, the lifecycle is controlled by the ReplicaSet and the replacement will be created immediately (even if the old Pod is still in a Terminating state). If you need an "at most" guarantee for your Pods, you should consider using a StatefulSet.


##### RollingUpdate

```yaml
apiVersion: apps/v1
kind: Deployment
spec:
  replicas: 36
  strategy:
    type: RollingUpdate
    rollingUpdate:
```
??? Note
    The Deployment updates Pods in a rolling update fashion when .spec.strategy.type==RollingUpdate. You can specify maxUnavailable and maxSurge to control the rolling update process.

###### MaxSurge

```yaml hl_lines="8"
apiVersion: apps/v1
kind: Deployment
spec:
  replicas: 36
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 25%
```
??? Note
    `.spec.strategy.rollingUpdate.maxSurge` is an optional field that specifies the maximum number of Pods that can be created over the desired number of Pods. The value can be an absolute number (for example, `5`) or a percentage of desired Pods (for example, `10%`). The value cannot be 0 if MaxUnavailable is 0. The absolute number is calculated from the percentage by rounding up. The default value is `25%`.

    For example, when this value is set to 30%, the new ReplicaSet can be scaled up immediately when the rolling update starts, such that the total number of old and new Pods does not exceed 130% of desired Pods. Once old Pods have been killed, the new ReplicaSet can be scaled up further, ensuring that the total number of Pods running at any time during the update is at most 130% of desired Pods.


###### maxUnavailable

```yaml hl_lines="9"
apiVersion: apps/v1
kind: Deployment
spec:
  replicas: 36
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
```
??? Note
    `.spec.strategy.rollingUpdate.maxUnavailable` is an optional field that specifies the maximum number of Pods that can be unavailable during the update process. The value can be an absolute number (for example, `5`) or a percentage of desired Pods (for example, `10%`). The absolute number is calculated from percentage by rounding down. The value cannot be 0 if `.spec.strategy.rollingUpdate.maxSurge` is `0`. The default value is `25%`.

    For example, when this value is set to 30%, the old ReplicaSet can be scaled down to 70% of desired Pods immediately when the rolling update starts. Once new Pods are ready, old ReplicaSet can be scaled down further, followed by scaling up the new ReplicaSet, ensuring that the total number of Pods available at all times during the update is at least 70% of the desired Pods.

#### Selector

```yaml hl_lines="4"
apiVersion: apps/v1
kind: Deployment
spec:
  selector:
```

##### matchLabels

Key Value pairs used to target the Pods later on.

Should be the same as [Labels](#labels) - But not required

| Name                             | Identical        |
|----------------------------------|------------------|
| `.metadata.labels`               | :material-close: |
| `.spec.template.metadata.labels` | :material-check: |

```yaml hl_lines="3"
spec:
  selector:
    matchLabels:
      component: web
      app.kubernetes.io/name: bradley
      app.kubernetes.io/instance: test
```

