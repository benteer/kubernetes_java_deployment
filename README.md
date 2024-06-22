# kubernetes_java_deployment
minikube project 

markdown
![Screenshot at 2024-06-22 14-22-51](https://github.com/benteer/kubernetes_java_deployment/assets/107338393/6d7d0d19-156a-4393-a089-95c6d64fedf7)

![Screenshot at 2024-06-22 14-32-16](https://github.com/benteer/kubernetes_java_deployment/assets/107338393/eed7350e-dc8e-4283-9368-b77be08f695c)
![Screenshot at 2024-06-22 14-33-46](https://github.com/benteer/kubernetes_java_deployment/assets/107338393/5aa1839d-edb6-4048-9cf0-6e5745e70846)

Copy code
# Project2 Minikube Setup

This guide provides instructions for setting up a Kubernetes cluster using Minikube for Project2.

## Prerequisites

- [Minikube](https://minikube.sigs.k8s.io/docs/start/) (latest version)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) (latest version)
- [Docker](https://docs.docker.com/get-docker/) (optional, if using Docker as the driver)

## Setup Steps

### 1. Install Minikube

Follow the official Minikube installation guide for your operating system: [Minikube Installation](https://minikube.sigs.k8s.io/docs/start/).

### 2. Start Minikube

Start Minikube with the desired driver (e.g., Docker, VirtualBox).

```sh
minikube start --driver=docker
If you want to specify a Kubernetes version or additional configurations, you can do so:

sh
Copy code
minikube start --driver=docker --kubernetes-version=v1.23.0
3. Verify Minikube Status
Ensure that Minikube is running correctly.

sh
Copy code
minikube status
4. Set Up Kubectl
Configure kubectl to use the Minikube context.

sh
Copy code
kubectl config use-context minikube
Verify the connection to your Minikube cluster.

sh
Copy code
kubectl get nodes
5. Deploy Your Application
Place your Kubernetes manifests (e.g., shopfront-service.yaml) in the project directory.

Apply the Kubernetes manifests to your Minikube cluster.

sh
Copy code
kubectl apply -f shopfront-service.yaml
6. Access Your Application
To access your application, you can use Minikube's service command.

sh
Copy code
minikube service <service-name>
Replace <service-name> with the name of your Kubernetes service defined in your manifest.


7. Troubleshooting
If you encounter issues, check the following:

Verify Minikube status: minikube status
Check the logs of your Minikube cluster: kubectl logs -n kube-system <pod-name>
Ensure your YAML files are correctly formatted and valid.
For example, to disable validation during deployment:

sh
Copy code
kubectl apply -f shopfront-service.yaml --validate=false
8. Additional Minikube Commands
Stop Minikube:

sh
Copy code
minikube stop
Delete Minikube cluster:

sh
Copy code
minikube delete
9. Resources
Minikube Documentation
Kubernetes Documentation
License
