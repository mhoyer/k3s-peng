# Argo CD - self-referring gitops setup

## Kick-off installation

Install via `helm`:

```bash
helm upgrade -i argo-cd oci://ghcr.io/argoproj/argo-helm/argo-cd --version 6.7.10 -f values.kick-off.yaml -n argocd --create-namespace
```

## See also

* https://argo-cd.readthedocs.io/en/stable/getting_started/
