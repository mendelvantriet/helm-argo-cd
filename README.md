# helm-argo

## Prepare cluster and docker images

```sh
kind create cluster

docker pull ...
kind load docker-image ...

```

## Install helm chart

```sh
helm dependency update
helm install argo .
kubectl get po
```

## Access web UI

    kubectl port-forward service/argo-argocd-server 8080:80

Go to `http://localhost:8080`.
Username: admin
Password: `kubectl get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d`


## Stop

```sh
helm delete argo
kind delete cluster
```

