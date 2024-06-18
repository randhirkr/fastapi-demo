# fastapi-demo
This is a sample containerized fastapi python application - tested locally on minikube(kubernetes).

### Prerequisite
Docker  
Kubectl

### Start local kubernetes cluster(minikube) and verify
```
minikube start --driver=docker
minikube status
minikube addons enable metrics-server
minikube addons list
minikube dashboard
```

### Create docker image and load into minikube
```
docker build -t helloimage:latest .
minikube image load helloimage:latest
```

### helm related command for chart creation and deployment
```
helm create hello-service
helm install hello-service-release ./hello-service
helm upgrade hello-service-release ./hello-service
helm uninstall hello-service-release
```

### Get the local deployment(minikube) URL and test it
```
minikube service hello-service-release --url
```

### Useful commands for troubeshoooting
```
kubectl get nodes -o wide
kubectl logs <pod-name>
kubectl get services
kubectl describe service <service-name>
kubectl describe pod <pod-name>
```

### cleanup
```
minikube stop
minikube delete --all
```