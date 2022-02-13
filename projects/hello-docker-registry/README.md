```
docker pull paulbouwer/hello-kubernetes:1.8
docker tag paulbouwer/hello-kubernetes:1.8 registry.k8s.dewep.net/paulbouwer/hello-kubernetes:1.8
docker push registry.k8s.dewep.net/paulbouwer/hello-kubernetes:1.8
```

```
kubectl apply -f projects/hello-docker-registry/hello-docker-registry.yml
```
