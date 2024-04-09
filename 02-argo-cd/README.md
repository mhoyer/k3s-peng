# Argo CD - self-referring gitops setup

## Kick-off installation

Install via `helm`:

```bash
helm upgrade -i argo-cd oci://ghcr.io/argoproj/argo-helm/argo-cd --version 6.7.10 -f values.kick-off.yaml -n argocd --create-namespace
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

## Make the installation self-referencing

Roll out the `Application` resource for Argo CD to self reference the existing installation with the git repo.

```bash
kubectl apply -f ./argo-cd.app.yaml
```

## See also

* https://argo-cd.readthedocs.io/en/stable/getting_started/
