# Kubernetes Workshop

Files supporting Kubernetes workshop sessions.

Each directory contains a dedicated ReadMe file.

## Dependencies 

- Minikube (Version: v1.15.1)
- kubectl (Version v1.19.3)

## Common executions

**Start a local cluster with Minikube:**

```shell script
minikube start --vm-driver=virtualbox --memory 5120 --kubernetes-version v1.18.3
```

**Enable dashboard**:

```shell script
minikube dashboard
```

**Enable Minikube tunnel for Load-Balancing services**:

```shell script
minikube tunnel
```

The tunnel simulates a load-balancer from an actual cloud service provider.