# simple-ecr-container-dani
simple nginx container + script to upload to AWS ECR

When I am doing some quick testing with Kubernetes or Docker I often need a small docker container to test things. This repo will serve that purpose. It has a very basic NGINX docker container with a simple web page. It also includes a script to build the container and push it to AWS ECR

### Setup
- create a AWS IAM user and attach the AmazonEC2ContainerRegistryFullAccess IAM policy
- click the user in IAM->Security Credentials -> create access key
- configure the aws cli on your machine (aws configure). enter the access key and set the region
- update build_and_push_to_ecr.sh with the container name and region you want
- create your private ECR repo in the AWS ECR console
- run build_and_push_to_ecr.sh to build the docker container and push it to ECR

### Kubernetes Deploy
- k3s/kubectl-apply.sh is a simple deployment aimed at a k3s host. It expects the amazon ecr setup i document in my tech-notes repo

![screenshot](/screenshots/dani-web.png "Dani website container deployed")
