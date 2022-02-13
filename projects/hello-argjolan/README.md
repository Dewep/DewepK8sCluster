```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install ingress-nginx --namespace cert-manager ingress-nginx/ingress-nginx --create-namespace
```

```
kubectl apply -f ./nginx-hello.yml
```

```
kubectl apply -f ./ingress.yml
```

```
helm repo add kubernetes-dashboard https://kubernetes.github.io/dashboard/
helm repo update
helm install kubernetes-dashboard --namespace kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard --create-namespace

kubectl apply -f ./dashboard-service-account.yml
kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user-token | awk '{print $1}')

export POD_NAME=$(kubectl get pods -n kubernetes-dashboard -l "app.kubernetes.io/name=kubernetes-dashboard,app.kubernetes.io/instance=kubernetes-dashboard" -o jsonpath="{.items[0].metadata.name}")
echo https://127.0.0.1:8443/
kubectl -n kubernetes-dashboard port-forward $POD_NAME 8443:8443
```

# Mauvis readme?
