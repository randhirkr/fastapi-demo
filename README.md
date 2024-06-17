# fastapi-demo
This is a sample containerized fastapi application - tested locally on minikube(kubernetes).

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