## Deploy database

**Create ConfigMaps for initialisation scripts

```shell
kubectl create configmap graphium-init --from-file=./init-db
```

**Create Peristent Volume for database files

```shell
kubectl apply -f database-pv.yml
```

**Create Deployment for database

```shell
kubectl apply -f database.yml
```

**List files injected via ConfigMaps**:

```shell
kubectl exec -it <POD_IDENTIFIER> -- /bin/bash -c 'ls -la /docker-entrypoint-initdb.d'
```

**Get logs of Postgis database**:

```shell
kubectl logs --tail=-1 --follow -l app=graphium-database
```

## Deploy Graphium server 

**Create Graphium deployment**:

````shell
kubectl apply -f graphium.yml
````

**Get logs of Graphium server**:

```shell
kubectl logs --tail=-1 --follow -l app=graphium-backend
```

**Open status page in browser**:

```shell
open $(minikube service --url graphium-backend)/graphium/api/status
```

## Deploy Graph-Viewer

**Add credentials for a private registry**:

Credentials are retrieved from Gitlab.

```shell
kubectl create secret docker-registry regcred --docker-server=<your-registry-server> --docker-username=<your-name> --docker-password=<your-pword> --docker-email=<your-email>
```

**Create Deployment**:

````shell
kubectl apply -f frontend.yml
````

**Open frontend in browser**:

```shell
open $(minikube service --url graph-viewer)
```