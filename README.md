# Kubernetes Deployment of Mongodb and Mongo-Express

This repository contains Kubernetes configuration files to set up MongoDB and Mongo Express services using `minikube`.

## Prerequisites

- `kubectl` installed
- `minikube` installed
- Docker Desktop or Docker installed (for local testing)
- Basic understanding of Kubernetes concepts

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/mongodb-mongo-express-k8s.git
   cd mongodb-mongo-express-k8s

2. Apply the Kubernetes manifests:

    ```bash
    kubectl apply -f mongodb-secret.yaml
    kubectl apply -f mongodb-configmap.yaml
    kubectl apply -f mongodb-deployment.yaml
    kubectl apply -f mongodb-service.yaml
    kubectl apply -f mongo-express-deployment.yaml
    kubectl apply -f mongo-express-service.yaml

3. Usage:
- Once the deployments are successfully applied, you can access Mongo Express UI via the external IP provided by the LoadBalancer service.

    ```bash
    minikube service mongo-express-service


## Components

### MongoDB Deployment
- A Kubernetes Deployment named mongodb-deployment is created with a single or multiple replicas.
- The MongoDB container is pulled from the official Mongo Docker image.
- Environment variables for MongoDB username and password are set using Kubernetes Secrets.
- MongoDB service is exposed internally within the cluster on port 27017.

### Mongo Express Deployment
- A Kubernetes Deployment named mongo-express-deployment is created with a single or multiple replicas.
- The Mongo Express container is pulled from the official Mongo Express Docker image.
- Environment variables for MongoDB connection details are set using Kubernetes Secrets and ConfigMaps.
- Mongo Express service is exposed externally using a LoadBalancer service on port 8081.

## Contributing
Contributions are welcome! Please feel free to open an issue or submit a pull request for any improvements or additional features.