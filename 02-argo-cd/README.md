# Argo CD - self-referring gitops setup

## Kick-off installation

Install via `helm`:

```bash
# kick-off install of the helm-chart itself w/o self-managing application
helm install argo-cd \
    --namespace argo-cd \
    --create-namespace  \
    --dependency-update \
    --set includeApplications=false \
    -f ./values.yaml \
    .

# now that ArgoCD CRDs are deployed, enable self-managed loop by upgrading
# the helm chart again including the ArgoCD self-management application.
helm install argo-cd \
    --namespace argo-cd \
    --create-namespace  \
    --dependency-update \
    --set includeApplications=true \
    -f ./values.yaml \
    .
```

Retrieve the generated `admin` password:

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d ; echo
```

### Uninstall

```bash
helm uninstall argo-cd -n argocd
```

## See also

* https://argo-cd.readthedocs.io/en/stable/getting_started/
