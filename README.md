# ArgoCD Deployment for Homepage

This document provides instructions for deploying the homepage application using ArgoCD. The deployment will generate the `homepage.default.k3s` webpage.

## Prerequisites

- ArgoCD installed and configured
- Kubernetes cluster (k3s) running

## Deployment Steps

1. **Create a new application in ArgoCD:**

    ```yaml
    apiVersion: argoproj.io/v1alpha1
    kind: Application
    metadata:
      name: homepage
      namespace: argocd
    spec:
      destination:
        namespace: default
        server: https://kubernetes.default.svc
      source:
        path: path/to/your/manifests
        repoURL: https://github.com/your-repo/homepage
        targetRevision: HEAD
      project: default
    ```

2. **Apply the manifest:**

    ```sh
    kubectl apply -f homepage-argocd.yaml
    ```

3. **Access the homepage:**

    Once the application is deployed, you can access it at `http://homepage.default.k3s`.

## Conclusion

Following these steps will deploy the homepage application using ArgoCD, making it accessible at `homepage.default.k3s`.
# homepage
