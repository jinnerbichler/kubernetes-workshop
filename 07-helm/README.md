## Deploy database

A list of available packages can be found here [https://artifacthub.io/](https://artifacthub.io/).

**Add the proper repository**:

```shell
helm repo add bitnami https://charts.bitnami.com/bitnami
```

**Create a dedicated namespace**:

```shell
kubectl apply -f namespace.yml
```

**Configure and install database**:

Configurable values can be found here: [https://artifacthub.io/packages/helm/bitnami/postgresql](https://artifacthub.io/packages/helm/bitnami/postgresql).

```shell
helm install -f postgres-values.yml -n helm database-07 bitnami/postgresql
```

## Deploy PGAdmin

**Add the proper repository**:

```shell
helm repo add runix https://helm.runix.net/
```

**Configure and install pgadmin**:

```shell
helm install -f pgadmin-values.yml -n helm pgadmin-07 runix/pgadmin4
```

**Open PGAdmin in the browser**:

```shell
minikube service pgadmin-07-pgadmin4 -n helm
```