# Backend
This Backend microservice have their own pipeline setup in your local Jenkins, the pipeline should consist of following steps
- Build application code
- Run Unit Tests if any
- Build a Docker image
- Push Docker image to your Dockerhub 
This repository also contains the manifests (docker-compose as well as Kubernetes) of the backend microservice. When the above pipeline of backend microservice runs, it will push a new docker image, so you will update the docker image in your manifest and apply it using docker-compose locally and using Minikube for Kubernetes. (Also support EKS but with few changes).
