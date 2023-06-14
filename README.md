# NAGP_2023_DEVOPS_ADVANCED_KUBERNETES_DOCKER

## Service API and MYSQL Database

- NodeJs API with 4 Pods
- MySQL Service with 1 Pod
    - Initialized MySQL with default `student` db and having `users` table with some entries

This repository contains the code for the Service API tier of the project. It provides an interface for interacting with the backend tier and retrieving records.

### Repository

The code repository for the Service API tier can be found at [GitHub](https://github.com/gauravgn90/NAGP_2023_DEVOPS_ADVACNED).

### Docker Images

The Docker images for the Service API tier can be found on Docker Hub.

- Nodejs API Service: [Docker Hub URL](https://hub.docker.com/layers/gauravgn90/kube-nodejs-api-image/v12/images/sha256-f7212e7c47356b429a4a0a1b39dd7c5de70a1ea2a63cb21aa4e643fa18c5a7e5?context=explore)

### Viewing Records

To view the records from the backend tier, you can access the following URL:

- Service API: [http://your-service-api-url/api-docs](http://your-service-api-url/api-docs)
    - Swagger UI interface will have the list all APIs

Make sure to replace `your-service-api-url` with the actual URL where your Service API is deployed.


### Folder Structure

This repository contains the Kubernetes YAML files and the API service code for the project.
- `api-service`: Contains the API service code.
  - `Dockerfile`: Dockerfile for building the API service image.
  - `app.js`: The main application code for the API service.
  - `package.json`: Packages used in the application

- `yamls`: Contains the Kubernetes YAML files.
  - `deployment.yaml`: YAML file for the deployment of the API service.
  - `service.yaml`: YAML file for the service definition.
  - `configmap.yaml`: YAML file for the configuration settings.
  - `ingress.yaml`: YAML file for the ingress configuration.

  - `manual-storageclass.yaml` :  Storage YAML file
  - `mysql-init-script.sql` : SQL init script file for reference
  - `mysql-config.yaml` : YAML file for the mysql config used in MYSQL deployment.
  - `mysql-pv.yaml` : YAML file for the MYSQL persistent volume.
  - `mysql-secret.yaml` : YAML file for the  MYSQL secrets service.
  - `mysql-deployment.yaml` : YAML file for the deployment of the MYSQL service.
  - `mysql-init-script-config.yaml` :  YAML file for the mysql init script configuration settings.
  - `webapp-deployment.yaml` : YAML file for the deployment of the API service.
  - `webapp-service.yaml` : YAML file for the deployment service of the API service.

### Usage

To use the Kubernetes YAML files and deploy the API service, follow the instructions below:

1. Make sure you have a Kubernetes cluster set up. Development purpose, make sure minikube is up and running.
2. Navigate to the `yamls` directory: `cd yamls`
3. Apply the Kubernetes YAML files:
    `kubectl apply -f "*.yaml"`
4. Monitor the deployment and check the status:
    `kubectl get pods`
    `kubectl get services`
5. Open webapp service using `minikube`
    `minikube service webapp --url`
    or
    `minikube service webapp` to open service api on browser
6. Access the API service using the provided endpoints.
    - Open `/api-docs` like [http://your-service-api-url/api-docs](http://your-service-api-url/api-docs)
    - Swagger UI will be opened
7.  For more details refer to the individual YAML files and the documentation.
