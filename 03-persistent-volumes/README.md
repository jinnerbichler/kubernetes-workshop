**Create Persistent Volume (PV)**:

```shell
kubectl apply -f persistent-volume.yml
```

**List Persistent Volumes**:

```shell
kubectl get pv
```

**Show details of specific PV**:

```shell
kubectl describe pv persistent-volume-03
```

**Create Persistent Volume Claim (PVC)**:

```shell
kubectl apply -f persistent-volume-claim.yml
```

**List Persistent Volumes Claims**:

```shell
kubectl get pvc
```

**Create multiple resource in one file**:

```shell
kubectl apply -f deployment.yml
```

**Accessing shell of pod/container**:

```shell
kubectl exec -it <PODNAME> -- /bin/bash
```

**Open Nginx on node port**:

```shell
minikube service persistent-volumes-03
```