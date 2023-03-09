### Use the following Repo to deploy the required infrastructure using Terraform
```https://github.com/amandhal/ec2_ecr.git```


### Use the following Repo to push images to Amazon ECR
```https://github.com/amandhal/clo835-assignment1.git```


### Login to EC2 instance
```ssh -i ~/.ssh/id_rsa ec2-user@<public_ip>```

Replace public_ip with the actual public_ip of deployed EC2 instance


### Clone this repo in the EC2 instance
```git clone https://github.com/amandhal/clo835-assignment2.git```


### Change directory
```cd clo835-assignment2```


### Install Docker
```Run ./docker-setup.sh```


### Logout and login to EC2 instance again and Change Directory


### Create Kind cluster
```Run ./kind-setup.sh```


### Create namespaces
```
kubectl create ns mysql
kubectl create ns web
```


### Create database pod
```kubectl apply -f mysql-pod.yaml -n mysql```


### Create service for database pod
```kubectl apply -f mysql-service.yaml -n mysql```


### Create application pod
```kubectl apply -f web-pod.yaml -n web```


### Create service for application pods
```kubectl apply -f web-service.yaml -n web```


### Create replicasets for database and application pods
```
kubectl apply -f mysql-rs.yaml -n mysql
kubectl apply -f web-rs.yaml -n web
```


### Create deployments for database and application pods
```
kubectl apply -f mysql-deployment.yaml -n mysql
kubectl apply -f web-deployment.yaml -n web
```
