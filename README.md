 Trend Application Deployment

## Project Overview
This project demonstrates Trend Application deployment using:

- React Application 
- Docker
- Jenkins CI/CD
- DockerHub
- AWS EKS (Kubernetes)
- LoadBalancer Exposure


## ⚙️ Steps followed:

### Clone Repository
git clone https://github.com/Gobika-kannan/Trend.git


### Docker Build
docker build -t gobikaka/trend-app .

docker run -d -p 3000:80 trend-app



### Push to DockerHub
docker tag trend-app gobikaka/trend-app:latest
docker push gobikaka/trend-app:latest



### Create EKS Cluster
eksctl create cluster \
--name trend-cluster \
--region ap-south-1 \
--nodegroup-name workers \
--node-type t3.medium \
--nodes 2

###  Kubernetes Deployment
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

## Jenkins CI/CD Pipeline

Pipeline stages:

1. Clone Code from GitHub
2. Build Docker Image
3. Push Image to DockerHub
4. Deploy Application to AWs
## Application URL

LoadBalancer DNS:
http://a5ad9f69f99a34eb1ae76e94ad61e27d-2100824263.ap-south-1.elb.amazonaws.com
