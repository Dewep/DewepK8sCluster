```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install ingress-nginx --namespace cert-manager ingress-nginx/ingress-nginx --create-namespace
```
