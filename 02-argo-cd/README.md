# Argo CD - self-referring gitops setup

## Kick-off installation

Install via `helm`:

```bash
helm dependency build ./kick-off
helm upgrade -i argo-cd -n argocd --create-namespace ./kick-off
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

## See also

* https://argo-cd.readthedocs.io/en/stable/getting_started/
