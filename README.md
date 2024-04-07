# Automated Application Deployment with ArgoCD

## Overview

This repository is part of an automated deployment pipeline using ArgoCD. It contains the application configuration for deploying the `wil42/playground` Docker image hosted on Docker Hub. ArgoCD monitors this repository to automatically sync and deploy changes to a Kubernetes cluster managed with k3s/k3d.

## ArgoCD Introduction

ArgoCD is a declarative, GitOps continuous delivery tool for Kubernetes. It automates the deployment of applications by syncing them to a desired state defined in a Git repository. ArgoCD enables the following features:

- **Automated Deployment**: Automatically deploys applications when changes are committed to the configured Git repository.
- **Declarative Setup**: Uses YAML files to manage applications and their environments.
- **Self-Healing**: Attempts to correct a drift from the desired configuration.
- **Visibility**: Offers a comprehensive UI and CLI for viewing application status and history.

## Manifests in this Repository

- `Deployment` (will-dpl): Defines the desired state of the application deployment, including the image to use (`wil42/playground:v1`) and the number of replicas.
- `Service` (will-svc): Specifies how the application pods are exposed within the Kubernetes cluster.
- `Ingress` (will-igs): Configures the ingress rules to manage external access to the application through HTTP.

## Connecting to ArgoCD

This project assumes ArgoCD is already installed and configured on your k3s/k3d cluster. ArgoCD will monitor this repository to automatically deploy new changes to your Kubernetes cluster.

- **Dashboard**: Access the ArgoCD dashboard through the ingress or using port-forwarding to manage and monitor the application deployments.


## Additional Information

For more detailed information on using ArgoCD, including advanced configurations and troubleshooting, please refer to the official [ArgoCD documentation](https://argo-cd.readthedocs.io/en/stable/).
