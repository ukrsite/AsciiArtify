# K3d & ArgoCD PoC

## Overview

This project demonstrates the setup of a Kubernetes cluster using k3d and the installation of ArgoCD for continuous delivery and GitOps workflows. Follow the steps below to get started.

[![asciicast](https://asciinema.org/a/vXisLL3Oj3BWzY97WduBhMVew.svg)](https://asciinema.org/a/vXisLL3Oj3BWzY97WduBhMVew)

## Steps

### Step 1: Deploy a Kubernetes Cluster using k3d

```bash
# Create a Kubernetes cluster
k3d cluster create argo

This command creates a Kubernetes cluster named argo using k3d.
```
### Step 2: Install ArgoCD

```bash
# Create the argocd namespace
kubectl create namespace argocd

# Apply the ArgoCD installation manifest
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

This step sets up the argocd namespace and installs ArgoCD using the provided manifest.
```
### Step 3: Access ArgoCD Graphical Interface
```bash
# Forward the ArgoCD server port
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Retrieve the initial admin password
ARGO_PASSWORD=$(kubectl get secret -n argocd argocd-initial-admin-secret -o jsonpath='{.data.password}' | base64 --decode)

# Access the ArgoCD interface
echo "ArgoCD URL: https://localhost:8080"
echo "Initial Admin Password: $ARGO_PASSWORD"

This step forwards the ArgoCD server port to localhost:8080, retrieves the initial admin password, and provides the ArgoCD interface URL along with the admin password.
```
## Conclusion
You have successfully set up a Kubernetes cluster and installed ArgoCD. For more details and advanced configurations, refer to the official documentation.

Feel free to explore the ArgoCD interface and use it for continuous delivery and GitOps practices
