# publiccharts
A personal approach on helm charts. 
We welcome all contributions

## Install charts

You can consume charts from either the classic Helm repository or OCI registry.

### Helm repository

```bash
helm repo add publiccharts https://k8sonlab.github.io/publiccharts
helm repo update
helm search repo publiccharts
helm install my-release publiccharts/<chart-name>
```

### OCI registry (GHCR)

```bash
helm registry login ghcr.io
helm pull oci://ghcr.io/k8sonlab/publiccharts/<chart-name> --version <chart-version>
helm install my-release oci://ghcr.io/k8sonlab/publiccharts/<chart-name> --version <chart-version>
```

Migration note:
- Preferred OCI path is `oci://ghcr.io/k8sonlab/publiccharts/<chart-name>`.
