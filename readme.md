# PoC ArgoCD Kubernetes ApplicationSets

Proof of concept to manage multiple applications based on cluster-labels.

! This is not production ready, feel free to use and edit for your own needs

```yaml
# https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#clusters
metadata:
    labels:
        # Install ArgoCD, based on this repository HEAD
        managedservices.argocd=HEAD
        # Install Kyverno, based on this repository HEAD
        managedservices.kyverno=HEAD
        # Target cluster version
        kubernetes.version=1.24
```

- Allows you to create a subset of working applications based on a specific Kubernetes version
- Develop and test specific applications and Charts in your own branch

## Hints:

- Install ArgoCD based on the [latest manifest](https://raw.githubusercontent.com/argoproj/argo-cd/master/manifests/ha/install.yaml)
- Make sure to add [this repository](applications/1.24/argocd/repositories.yaml) to ArgoCD
- Add the [application](applications/1.24/argocd/application.yaml) that will sync all the [ApplicationSets](applicationSets)
