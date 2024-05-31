# Kyverno Wrapper Chart

To render locally:

```bash
helm template "kyverno" . --dependency-update --set kyverno.crds.install=false
```
