**Create/update multiple resources**:

```shell
kubectl apply -f configmap.yml -f service.yml -f secret.yml -f deployment.yml
```

**Access NodePort of Service**:

```shell
minikube service configmaps-secrets-02
```

**Show details of ConfigMap**:

```shell
kubectl describe configmap configmap-02
```

**Show details of Secret**:

```shell
kubectl describe secret secret-02
```

**Restart deployment manually**:

```shell
kubectl rollout restart deployment configmaps-secrets-02
```

```shell
minikube service configmaps-secrets-02
```

### Notes:

- Changes in ConfigMaps / Secrets are not directly effecting deployments...deployments must be restarted.