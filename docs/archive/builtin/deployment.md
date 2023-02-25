---
title: "Deployment"
---

## What is a `deployment`

A Deployment provides declarative updates for Pods and ReplicaSets.

You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired 
state at a controlled rate. You can define Deployments to create new ReplicaSets, or to remove existing Deployments and adopt all their resources with new Deployments.

??? note "Example"

    ```yaml
    apiVersion: apps/v1 # (1)!
    kind: Deployment # (2)!
    metadata: 
      name: hello
      namespace: default
    spec:
      replicas: 3
      selector:
        matchLabels:
          run: hello-v1
      template:
        metadata:
          labels:
            run: hello-v1
        spec:
          containers:
            - image: us-docker.pkg.dev/google-samples/containers/gke/hello-app:1.0
              imagePullPolicy: IfNotPresent
              name: hello-v1
              ports:
                - containerPort: 8080
                  protocol: TCP
    ```

    1.   [API Documentation](#api-version)
    2.   [Kind Documentation](#kind)


    

---


######



```yaml
  template:
    metadata:
      annotations:
        checksum/config: testsa
        checksum/secret: testsa
      labels:
        component: web
        app.kubernetes.io/name: bradley
        app.kubernetes.io/instance: test
    spec:
      serviceAccountName: bradley
      securityContext:
        {}
      containers:
        - name: bradley
          securityContext:
            {}
          image: ""
          imagePullPolicy: IfNotPresent
          ports:
            - name: http
              containerPort: 80
              protocol: TCP
          livenessProbe:
            httpGet:
              httpHeaders:
                - name: Host
                  value: "localhost"
              path: /ping
              port: http
          readinessProbe:
            httpGet:
              httpHeaders:
                - name: Host
                  value: "localhost"
              path: /ping
              port: http
          startupProbe:
            httpGet:
              httpHeaders:
                - name: Host
                  value: "localhost"
              path: /ping
              port: http
          envFrom:
            - configMapRef:
                name: test-audiences
            - secretRef:
                name: test-audiences


          resources:
            {}
```

```json

```