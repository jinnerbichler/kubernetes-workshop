**Create/update deployment**:

```shell
kubectl apply -f deployment.yml --record
```

**Show deployment history**:

```shell
kubectl rollout history deploy/hello-kubernetes
```

**Details of deployment**:

```shell
kubectl rollout history deploy/hello-kubernetes --revision=5
```

**Undo deployment**:

```shell
kubectl rollout undo deploy/hello-kubernetes --to-revision=5
```

### Update strategies

- RollingUpdate: a rolling update waits for new pods to become ready via your readiness probe before it starts scaling down the old ones.
- Recreate: all the old pods are killed all at once and get replaced all at once with the new ones.
- Canary: both versions co-exists, whereas only a defined percentage of request are forwarded to the newer release.

### Useful kubectl commands

Note: all namespaces objects in the namespace `default` are shown if no namespace is referred.

**List deployments**:

```shell
kubectl get deployments
```

**Show details of deployment**:

```shell
kubectl describe deployments hello-kubernetes-00
```

**Show details of service**:

```shell
kubectl describe services hello-kubernetes-00
```

**List services**:

```shell
kubectl get services
```

**Display current cluster configuration of client**:

```shell
kubectl config view
```

**List all available resources**:

```shell
kubectl api-resources
```

TODO: Minikube commands for accessing nodeport
TODO: Command for accessing logs
TODO: explain internal DNS based on name of Service