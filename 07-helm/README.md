## Deploy database

A list of available packages can be found here [https://artifacthub.io/](https://artifacthub.io/).

**Create a dedicated namespace**:

```shell
kubectl apply -f namespace.yml
```

**Add the proper repository**:

```shell
helm repo add bitnami https://charts.bitnami.com/bitnami
```

**Configure and install database**:

Configurable values can be found here: [https://artifacthub.io/packages/helm/bitnami/postgresql](https://artifacthub.io/packages/helm/bitnami/postgresql).

```shell
helm install -f postgres-values.yml -n helm database-07 bitnami/postgresql
```

**Update Helm package**:

```shell
helm upgrade -f postgres-values.yml -n helm database-07 bitnami/postgresql
```

## Deploy PGAdmin

Configurable values can be found here: [https://artifacthub.io/packages/helm/runix/pgadmin4](https://artifacthub.io/packages/helm/runix/pgadmin4).

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