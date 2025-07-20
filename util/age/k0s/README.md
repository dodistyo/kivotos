# Kind Cluster Setup

## Introduction

This guide will help you set up a local Kubernetes cluster using Kind (Kubernetes in Docker) with the pre-existing `kivotos-cluster.yaml` configuration file.

## Prerequisites

- Install **Docker**: [Get Docker](https://docs.docker.com/get-docker/)
- Install **Kind**: [Install Kind](https://kind.sigs.k8s.io/)
- Install **kubectl**: [Install kubectl](https://kubernetes.io/docs/tasks/tools/)

## Quick Start

1. Ensure you have `kivotos-cluster.yaml` in your directory.

2. Create your cluster with:

   ```sh
   kind create cluster --config kivotos-cluster.yaml
   ```

3. Confirm your cluster is running:

   ```sh
   kubectl cluster-info --context kind-kind
   ```

## Useful Commands

- **Cluster Info**: `kubectl cluster-info`
- **List Nodes**: `kubectl get nodes`
- **Delete Cluster**: `kind delete cluster`

## Troubleshooting

- Ensure Docker is running and properly configured.
- Verify compatibility of `kubectl` and `kind` versions.