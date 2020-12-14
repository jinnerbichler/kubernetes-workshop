**List namespaced resources**:

```shell
kubectl api-resources --namespaced=true
```

**Create Namespaces**:

```shell
kubectl apply -f namespaces.yml
```

**List Namespaces**:

```shell
kubectl get namespaces
```

**Deploy to a specific namespace**:

```shell
kubectl apply -f deployment.yml --namespace=development
```

### Namespaces and DNS ([more info](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/))

When you create a Service, it creates a corresponding DNS entry. 
This entry is of the form <service-name>.<namespace-name>.svc.cluster.local, which means that if a container just uses <service-name>, it will resolve to the service which is local to a namespace.
This is useful for using the same configuration across multiple namespaces such as Development, Staging and Production. 
If you want to reach across namespaces, you need to use the fully qualified domain name (FQDN).

