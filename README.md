# Milvus Operator

[![CI Pipeline](https://github.com/milvus-io/milvus-operator/actions/workflows/ci.yml/badge.svg)](https://github.com/milvus-io/milvus-operator/actions/workflows/ci.yml/badge.svg)
[![codecov](https://codecov.io/gh/milvus-io/milvus-operator/branch/main/graph/badge.svg?token=DAXmgusBQq)](https://codecov.io/gh/milvus-io/milvus-operator)
[![Go Reference](https://pkg.go.dev/badge/github.com/milvus-io/milvus-operator.svg)](https://pkg.go.dev/github.com/milvus-io/milvus-operator)
<img src="https://img.shields.io/github/license/milvus-io/milvus" alt="license">


> **ATTENTIONS:** THE `MAIN` BRANCH MAY BE IN AN UNSTABLE OR EVEN BROKEN STATE DURING DEVELOPMENT.

## Overview
[Milvus](https://milvus.io) is a cloud-native, open-source vector database built to manage embedding vectors generated by machine learning models and neural networks. It extends the capabilities of best-in-class approximate nearest neighbor (ANN) search libraries (e.g. Faiss, NMSLIB, Annoy) and features on-demand scalability, and high availability.

The Milvus Operator provides an easy and solid solution to deploy and manage a full Milvus service stack including both the milvus components and its relevant dependencies such as etcd, pulsar and minio to the target [Kubernetes](https://kubernetes.io/) clusters in a scalable and high-available way. The Milvus Operator defines a milvuscluster custom resources on top of Kubernetes [Custom Resources](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/). The Kubernetes API can then be used in a declarative way to manage Milvus deployment stack and ensure its scalability and high-availability operation.

# Getting started
## Deploy milvus operator
```shell
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.5.3/cert-manager.yaml
kubectl apply -f https://raw.githubusercontent.com/milvus-io/milvus-operator/main/deploy/manifests/deployment.yaml
```

For more infomation Check [instructions on how to install/uninstall milvus operator](docs/installation/installation.md)

## Create milvus cluster
```shell
kubectl apply -f https://raw.githubusercontent.com/milvus-io/milvus-operator/main/config/samples/milvuscluster_default.yaml
```

# Versioning

Versions of the underlying components are listed below:

<!-- source csv for table
Components, Milvus, Pulsar, Etcd, MinIO
Versions, 2.0.0-rc8 `[1]`, 2.7.3, 3.5.0,2021.10.6 -->

|Components| Milvus| Pulsar| Etcd| MinIO|
|---|---|---|---|---|
|Versions| 2.0.0-rc8 `[1]`| 2.7.3| 3.5.0|2021.10.6|


**NOTES:**

`[1]` Version of milvus is the default version we will use, you can set it to other version. The Compatibility with milvus releases is showed below.

## Compatibility With Milvus Releases

<!-- source csv for table
Milvus Versions, 1.x, 2.0.0-rc1-2.0.0-rc8
Compatibility, :heavy_multiplication_x:, :heavy_check_mark: -->

|Milvus Versions| 1.x| 2.0.0-rc1-2.0.0-rc8|
|---|---|---|
|Compatibility| :heavy_multiplication_x:| :heavy_check_mark:|



**NOTES:**

  :heavy_check_mark: : support
  :heavy_multiplication_x: : not support


# Documentation
- [How it works](docs/arch/arch.md)
- [Installation](docs/installation/installation.md)
- [How to configure the MilvusCluster](docs/CRD/milvus-cluster.md)
- How to configure dependencies:
    - [etcd](config/assets/charts/etcd/README.md)
    - [minio](config/assets/charts/minio/README.md)
    - [pulsar](config/assets/charts/pulsar/README.md)
- [Install KinD for development](docs/installation/kind-installation.md)

