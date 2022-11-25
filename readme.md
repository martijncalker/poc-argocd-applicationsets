# PoC ArgoCD Kubernetes ApplicationSets

Proof of concept to manage multiple applications based on cluster-labels.

```yaml
# https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/#clusters
metadata:
    labels:
        # Install App on cluster
        nl.vancalker.managedservices/argocd-install=true 
        # Specify version; branch, tag or hash
        nl.vancalker.managedservices/argocd-install-version=HEAD 
        # Target cluster version
        version=1.24
```

Should allow you to create a subset of working applications based on a specific Kubernetes version. 
