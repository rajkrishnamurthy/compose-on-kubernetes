# Install on Azure AKS

## Pre-requisites
- To install Compose on Kubernetes on Azure AKS, you must create an AKS cluster with RBAC enabled.
- To install etcd using these instructions, you must have [Helm](https://helm.sh) in your client environment.
- [Download the Compose on Kubernetes installer](https://github.com/docker/compose-on-kubernetes/releases).

## Create compose namespace

Just run `kubectl create namespace compose`.

## Deploy etcd

If you already have an etcd instance, skip this.
Otherwise, please follow [How to deploy etcd](./deploy-etcd.md).

## Deploy Compose on Kubernetes

Run `installer-[darwin|linux|windows.exe] -namespace=compose -etcd-servers=http://compose-etcd-client:2379 -tag=v0.4.18`.

**Note: To setup Mutual TLS with the etcd instance, you can use `etcd-ca-file`, `etcd-key-file` and `etcd-cert-file` flags.**
