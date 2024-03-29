# seed-kubernetes

## Installation
1. [Docker](https://docs.docker.com/compose/install/)
2. [Kind](https://kind.sigs.k8s.io/docs/user/quick-start)
3. [Kubectl](https://kubernetes.io/docs/reference/kubectl/)

## Notes
* OS used: Linux.
* Maybe it's needed to run the installation and commands with sudo.

## Config file
when a cluster is created, the file `config` is created inside `~/.kube/`. This file holds the context to connect with the cluster

## Kind Configuration
[Configuration](https://kind.sigs.k8s.io/docs/user/configuration/)

# Commands

## Command create cluster
`kind create cluster`
## Command to set context
`kubectl cluster-info --context kind-kind`
## Command to get nodes
`kubectl get nodes`
## Command to get a cluster
`kind get clusters`
## Command to delete a cluster
`kind delete clusters cluster_name`
## Command to init clusters from .yaml file
`kind create cluster --config=k8s/config.yaml --name=knowledge`
## command to get contexts
`kubectl config get-clusters`
## command to switch contexts
`kubectl config use-context foo`

# Image with app to test kubernetes
* Go app on `server.go`
* Create Dockerfile for image
* Build an image containing the app. `docker build -t name/my-app .`
* Run app. `docker run --rm -p 80:80 name/myApp`
* push your image to docker hub.

# Pods
* Create `pod.yaml` file.
* Command to apply: `kubectl apply -f k8s/pod.yaml`.
* Command to get pods: `kubectl get pods`.
* Command to delete pods: `kubectl delete pod name`.
* Forward: `kubectl port-forward pod/goserver 8000:80`.
* task `localhost:8000`.
* Command do describe pod: `kubectl describe pod name`.

# ReplicaSet
* Create `replicasete.yaml` file.
* Command to apply: `kubectl apply -f k8s/replicaset.yaml`.
* Command to get replicasets: `kubectl get replicasets`.
* Command to delete replicasets: `kubectl delete replicaset name`.
* Forward `kubectl port-forward replicaset/goserver-6c8668f6d5 8000:80`.

# Deployments
* Create `deployment.yaml` file.
* Command to apply: `kubectl apply -f k8s/deployment.yaml`.
* Command to get deployments: `kubectl get deployments`.
* Command to delete deployments: `kubectl delete deployment name`.
* Forward `kubectl port-forward deployment/goserver 8000:80`.

# Variables
* Create `configmap-env.yaml`.
* Command to appy: `kubectl apply -f k8s/configmap-env.yaml`.

# Services 
## ClusterIp
* Create `serrvice.yaml` file.
* Command to apply `kubectl apply -f k8s/service.yaml`.
* Forward `kubectl port-forward service/goserver-service 8000:80`.
* Note: `targetPort` redirect to container port, if your app/container has port 10 by example, then `targetPort` must be equals to 10. When you task `localhost:8000` the service will redirect to 80, that redirects to 10. 

## NodePort
* When the type is `NodePort`, it's needed to establish a port or let randomly, this kind of port will make a connection with all pods

## LoadBalance
* Create `service-load-balancer.yaml`.
* Note: This kind of service, will create an external ip.


# Rolloout
* Command to get history `kubectl rollout history deployment name`.
* Command to undo `kubectl rollout undo deployment name`.
* command to undo with revision `kubectl rollout undo deployment name --to-revision=n`

# Proxy to kubernet apis
* Commanto to establish the proxy `kubectl proxy --port=8080`.


