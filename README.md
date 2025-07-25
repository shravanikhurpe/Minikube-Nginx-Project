# Minikube-Nginx-Project
Git Docker Kubernetes | Minikube Webserver Project

1. Launch EC2 Instance - SSH to it.
2. Install git and clone this repository
```
git clone https://github.com/atulkamble/Minikube-Nginx-Project.git
cd Minikube-Nginx-Project
```
```
docker login
cd D:/project
cd .\k8snginx\
New-Item index.html
nano index.html
New-Item Dockerfile
nano Dockerfile
docker build -t my-nginx-image .
docker tag my-nginx-image atuljkamble/my-nginx-image:latest
sudo docker push atuljkamble/my-nginx-image:latest
docker run -p 80:80 atuljkamble/my-nginx-image

New-Item nginx-deployment.yaml
nano nginx-deployment.yaml
kubectl apply -f nginx-deployment.yaml

New-Item nginx-service.yaml
nano nginx-service.yaml
kubectl apply -f nginx-service.yaml

minikube service nginx-service
kubectl get pods
kubectl get svc nginx-service --watch
minikube dashboard

kubectl expose deployment nginx-deployment --type=LoadBalancer --port=80
minikube service nginx-deployment
minikube addons enable ingress

```

