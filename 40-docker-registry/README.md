```
helm repo add twuni https://helm.twun.io
helm repo update
docker run --rm -ti xmartlabs/htpasswd dewep XYZXYZXYZXYZ
helm install docker-registry --namespace docker-registry twuni/docker-registry --create-namespace -f chart_values.yml --set 'secret.htpasswd=dewep:$2y$05$/sj0flN17lfOmZyejCODAe8OkNtD8CuhGMaAy2sC9ZQL25qnNHQ1.'
```

```
helm repo add bryanalves https://bryanalves.github.io/helm-charts
helm repo update
helm install docker-registry-ui --namespace=docker-registry bryanalves/registry-ui
kubectl get pods --namespace docker-registry -l "app.kubernetes.io/name=registry-ui,app.kubernetes.io/instance=docker-registry-ui" -o jsonpath="{.items[0].metadata.
name}"
kubectl port-forward --namespace docker-registry docker-registry-ui-7b5cb76dfd-xmrn4 8080:80
```

```
docker login registry.k8s.dewep.net
kubectl create secret docker-registry regcred --docker-server=registry.k8s.dewep.net --docker-username=dewep --docker-password=XYZXYZXYZXYZ
```
