# k3s - A local Kubernetes test cluster

Install in WSL2:

```bash
curl -sfL https://get.k3s.io | K3S_KUBECONFIG_MODE="644" sh -
```

Check if it's running:

```bash
systemctl status k3s
k3s kubectl get nodes
```

## Improve UX in Bash

Just source the `KUEBCONFIG` environment variable:

```bash
source ./env.sh
```

Now you can:

```bash
kubectl cluster-info
kubectl get nodes
```

## See also

* https://docs.k3s.io/quick-start
