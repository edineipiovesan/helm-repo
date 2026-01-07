# Helm Repository

This directory contains a local Helm chart repository for the ArgoCD Control Plane project. It hosts packaged Helm charts that can be installed using Helm or integrated with ArgoCD.

## Adding the Repository

To add this repository to your local Helm client:

```bash
helm repo add argocd-controlplane file:///absolute/path/to/helm-repo
helm repo update
```

**Note**: Replace `/absolute/path/to/helm-repo` with the full path to this `helm-repo` directory on your system.

## Available Charts

- **data-materializer**: A Helm chart for deploying the data materializer application on Kubernetes.
  - Version: 0.0.1
  - Description: A Helm chart for Kubernetes

## Installing Charts

Once the repository is added, you can install charts using:

```bash
helm install <release-name> argocd-controlplane/<chart-name>
```

Example:
```bash
helm install data-mat argocd-controlplane/data-materializer
```

## For ArgoCD Integration

This repository can be used as a Helm source in ArgoCD Applications. Configure the repository URL as `file:///absolute/path/to/helm-repo` in your ArgoCD repository settings.

## Maintaining the Repository

To update the repository index after adding new charts:

```bash
helm repo index .
```

To package a new chart version:

```bash
helm package ../data-materializer
```
