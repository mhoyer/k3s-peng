# External Secrets Wrapper Chart

To render locally:

```bash
helm template "external-secrets" . --dependency-update --set external-secrets.installCRDs=false
```
