# Hello World Helm Chart

This Helm chart deploys a simple "Hello World" application to a Kubernetes cluster.

## Prerequisites

- Kubernetes 1.16+
- Helm 3.0+

## Installation

### Add the Helm Repository
To use this chart, add your Helm repository:

```bash
helm repo add my-repo https://example.com/charts
helm repo update
```
# Summary of The Configurations
### Deployment and Scaling
The chart is set to deploy **2 replicas** of the application and has autoscaling enabled, allowing the application to scale between **2 and 5 replicas** based on CPU usage.

### Container Image and Secrets
The application uses an image hosted in a private Azure Container Registry (`mycontainerregistryteldahtest.azurecr.io/helloworld`), with an image pull secret (`acr-secret`) configured for authentication.

### Service Configuration
A Kubernetes `ClusterIP` service exposes the application internally within the cluster on port **3000**, and it operates in the `app` namespace.

### Service Account
- A service account is created and automatically mounts API credentials to the application pods.

---

## Summary of Your Configuration

1. **Replicas**: Deploys 2 replicas with autoscaling up to 5 based on 70% CPU usage.
2. **Image**: Uses a private image from Azure Container Registry with tag `74` and a pull secret.
3. **Service**: Exposes the application internally on port 3000 within the `app` namespace.

This configuration ensures a functional deployment with the flexibility to scale and adapt to cluster resource availability while keeping security and external access minimal for now.
