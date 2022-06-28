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

# Cluster

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

# Kind Configuration

[Configuration](https://kind.sigs.k8s.io/docs/user/configuration/)

## Command to init clusters from .yml file
`kind create cluster --config=k8s/config.yaml --name=knowledge`