# PoC ArgoCD Kubernetes ApplicationSets

Proof of concept to manage multiple applications based on cluster-labels.

```yaml
# https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#clusters
metadata:
    labels:
        # Install ArgoCD
        nl.vancalker.managedservices.argocd/install=true 
        # Specify this repo revision (branch, HEAD, tag, SHA)
        nl.vancalker.managedservices.argocd/version=HEAD 
        # Target cluster version
        version=1.24
```

- Allows you to create a subset of working applications based on a specific Kubernetes version
- Develop and test specific applications and Charts in your own branch, referance that branch via `{app}/version`
