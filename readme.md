# PoC ArgoCD Kubernetes ApplicationSets

Proof of concept to manage multiple applications based on cluster-labels.

! This is not production ready, feel free to use and edit for your own needs

```yaml
# https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#clusters
metadata:
    labels:
        # Install ArgoCD
        managedservices.argocd/install=true 
        # Specify this repo revision (branch, HEAD, tag, SHA)
        managedservices.argocd/version=HEAD 
        # Target cluster version
        version=1.24
```

- Allows you to create a subset of working applications based on a specific Kubernetes version
- Develop and test specific applications and Charts in your own branch, referance that branch via `{app}/version`

## Hints:

- Install ArgoCD based on the [latest manifest](https://raw.githubusercontent.com/argoproj/argo-cd/master/manifests/ha/install.yaml)
- Make sure to add [this repository](applications/1.24/argocd/repositories.yaml) to ArgoCD
- Add the [application](applications/1.24/argocd/application.yaml) that will sync all the [ApplicationSets](applicationSets)
