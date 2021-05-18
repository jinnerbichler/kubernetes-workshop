**Create/update deployment**:

```shell
kubectl apply -f deployment.yml --record
```

**Create service**:

```shell
kubectl apply -f service.yml
```

**Show logs of deployment**:

```shell
kubectl logs --tail=-1 --follow -l app=hello-kubernetes-01
```

**Show deployment history**:

```shell
kubectl rollout history deploy/hello-kubernetes-01
```

**Details of deployment**:

```shell
kubectl rollout history deploy/hello-kubernetes-01 --revision=5
```

**Undo deployment**:

```shell
kubectl rollout undo deploy/hello-kubernetes-01 --to-revision=5
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
kubectl describe deployments hello-kubernetes-01
```

**Show details of service**:

```shell
kubectl describe services hello-kubernetes-01
```

**List services**:

```shell
kubectl get services
```

**Open NodePort of service in browser**:

```shell
minikube service hello-kubernetes-01
```

**Display current cluster configuration of client**:

```shell
kubectl config view
```

**List all available resources**:

```shell
kubectl api-resources
``` 