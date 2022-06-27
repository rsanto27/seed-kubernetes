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

## Cluster

## command create cluster
`kind create cluster`
## command to set context
`kubectl cluster-info --context kind-kind`
## command to get nodes
`kubectl get nodes`
## command to get a cluster
`kind get clusters`
## command to delete a cluster
`kind delete clusters cluster_name`