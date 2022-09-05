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
## Command to init clusters from .yml file
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
* Forward: `kubectl port-forward pod/goserver 8000:80`.
* task `localhost:8000`.