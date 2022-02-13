```
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.7.1/cert-manager.crds.yaml
helm repo add jetstack https://charts.jetstack.io
helm repo update
helm install cert-manager --namespace cert-manager --version v1.7.1 jetstack/cert-manager --create-namespace
kubectl apply -f ./ssl-test/cert-manager.yml
```
