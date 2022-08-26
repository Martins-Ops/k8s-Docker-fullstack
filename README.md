# A Full Stack Dockerize NodeJS

Write a basic Node.js/Express application that responds to several routes and communicates with MongoDB or SQLite to save and retrieve some information (e.g. a person, a pet, a car, you choose)

Having written the application, write several unit tests (using Mocha/Chai or Jest) to ensure the application behaves as expected.

Dockerise your application, and demonstrate running it in a container locally (on your computer)

Extra 1: Ensure good code style with ESLint
Extra 2: Create a basic Kubernetes Helm chart for the app and deploy (locally in Minikube or on the cloud).

## OS Requirement

- Install NodeJS
- Install Docker
- Install Kubernetes
- Install Minikube
- MongoDB


## Run Locally without Docker / Kubernetes



- Edit mongodb config.js file in the root of your project to your mongodb URL
- Run npm install
- Run npm start
- Go to http://localhost:5000

## Run with Docker / Kubernetes / Minikube / EKS

```bash

# Run npm install
npm install

# Build docker image
docker image build -t node-image .

# Docker login with credentials
docker login

# To get image ID use command - `docker image ls`
# Create a tag for docker image
docker tag <IMAGE_ID> <DOCKER_USERNAME>/node-image:full-stack

# Docker push
docker push <DOCKER_USERNAME>/node-image

In this project I made use of Amazon (AWS) EKS for Kubernetes provisioning and AWS ECR for containerizng.

# Create service and pod for NodeJS and MongoDB
kubectl create -f node-service.yaml

kubectl create -f node-controller.yaml

kubectl create -f mongo-service.yaml

kubectl create -f mongo-controller.yaml


# Get IP ADD | NODEPORT use  command below
- kubectl describe svc full-Stack

- NodePort ip

```

## View app
http://NODEPORT_IP_ADDRESS:30000


## Run ESLint Locally
npm run lint

## Run API test Locally
npm run test

### Output of the Deployment


![app-image](app-image.JPG)
