# node-red

![Version: 1.0.1](https://img.shields.io/badge/Version-1.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.1.2](https://img.shields.io/badge/AppVersion-4.1.2-informational?style=flat-square)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue)](https://opensource.org)

Node-Red helmchart, based on nodered image. A nice web ui flow tool

**Homepage:** <https://nodered.org/>

## Install

You can install this chart from the classic Helm repository or from OCI in GHCR.

### Helm repository

```bash
helm repo add publiccharts https://charts.ar80.eu
helm repo update
helm install my-release publiccharts/node-red
```

### OCI registry (GHCR)

```bash
helm registry login ghcr.io
helm install my-release oci://ghcr.io/k8sonlab/publiccharts/node-red --version <chart-version>
```

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| varet80 |  | <https://github.com/varet80> |
## Source Code

* <https://github.com/k8sonlab/publiccharts>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| deploymentStrategy | string | `""` | Specifies the strategy used to replace old Pods by new ones, default: `RollingUpdate` |
| image.registry | string | `"docker.io"` | The image registry to pull from |
| image.repository | string | `"nodered/node-red"` | The image repository to pull from |
| image.pullPolicy | string | `"IfNotPresent"` | The image pull policy |
| image.tag | string | `""` | The image tag to pull, default: `Chart.appVersion` |
| rbac.enabled | bool | `true` |  |
| rbac.createClusterRole | bool | `false` | Create a ClusterRole resource for the node-red pod. default: false |
| imagePullSecrets | string | `""` | The image pull secrets |
| nameOverride | string | `""` | Provide a name in place of node-red |
| fullnameOverride | string | `""` | String to fully override "node-red.fullname" |
| npmrc.enabled | bool | `false` | Enable custom npmrc config |
| npmrc.registry | string | `"https://registry.npmjs.org"` | Configuration to use any compatible registry |
| npmrc.content | string | `"# Custom npmrc config\n"` | Configuration to add custom npmrc config |
| env | list | `[]` | node-red env, see more environment variables in the [node-red documentation](https://nodered.org/docs/getting-started/docker) |
| projectMode | object | `{"enabled":false}` | Enable Node-RED project mode for Git integration and project management Note: Project mode requires write access to the /data directory and may need additional security context adjustments depending on your cluster's security policies |
| envFrom | list | `[]` |  |
| serviceAccount.create | bool | `true` | Create service account |
| serviceAccount.annotations | object | `{}` | Additional ServiceAccount annotations |
| serviceAccount.name | string | `""` | Service account name to use, when empty will be set to created account if |
| podAnnotations | object | `{}` | Pod annotations |
| deploymentAnnotations | object | `{}` | Deployment annotations |
| podSecurityContext | object | `{"fsGroup":1000,"runAsUser":1000}` | Pod Security Context see [values.yaml](values.yaml) |
| podSecurityContext.fsGroup | int | `1000` | node-red group is 1000 |
| podSecurityContext.runAsUser | int | `1000` | node-red user is 1000 |
| securityContext | object | `{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"privileged":false,"readOnlyRootFilesystem":false,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000,"seccompProfile":{"type":"RuntimeDefault"}}` | Security Context see [values.yaml](values.yaml) |
| service.type | string | `"ClusterIP"` | Kubernetes service type |
| service.port | int | `1880` | Kubernetes port where service is exposed |
| service.annotations | object | `{}` | Annotations for the service |
| metrics.enabled | bool | `false` | Deploy metrics service |
| metrics.path | string | `"/metrics"` |  |
| metrics.serviceMonitor.enabled | bool | `false` | Enable a prometheus ServiceMonitor |
| metrics.serviceMonitor.basicAuth | object | `{}` | Prometheus basicAuth configuration for ServiceMonitor endpoint |
| metrics.serviceMonitor.interval | string | `"30s"` | Prometheus ServiceMonitor interval |
| metrics.serviceMonitor.relabelings | list | `[]` | Prometheus [RelabelConfigs] to apply to samples before scraping |
| metrics.serviceMonitor.metricRelabelings | list | `[]` | Prometheus [MetricRelabelConfigs] to apply to samples before ingestion |
| metrics.serviceMonitor.selector | object | `{}` | Prometheus ServiceMonitor selector |
| metrics.serviceMonitor.namespace | string | `""` | Prometheus ServiceMonitor namespace |
| metrics.serviceMonitor.additionalLabels | object | `{}` | Prometheus ServiceMonitor labels |
| persistence.enabled | bool | `false` | Use persistent volume to store data |
| persistence.accessMode | string | `"ReadWriteOnce"` | Persistence access mode |
| persistence.size | string | `"5Gi"` | Size of persistent volume claim |
| persistence.keepPVC | bool | `false` | ## Keep a created Persistent volume claim when uninstalling the helm chart (default: false) |
| initContainers | list | `[]` | containers which are run before the app containers are started |
| ingress.enabled | bool | `false` | Enable an ingress resource for the server |
| ingress.className | string | `""` | Defines which ingress controller will implement the resource |
| ingress.annotations | object | `{}` | Additional ingress annotations |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0] | object | `{"path":"/","pathType":"ImplementationSpecific"}` | The base path |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` | Ingress type of path |
| ingress.tls | list | `[]` | Ingress TLS configuration |
| httpRoute.enabled | bool | `false` | Enable an HTTPRoute resource for the server |
| httpRoute.annotations | object | `{}` | Additional HTTPRoute annotations |
| httpRoute.parentRefs | list | `[]` | Parent references for Gateway API attachment |
| httpRoute.hostnames | list | `[]` | Hostnames exposed by the HTTPRoute |
| httpRoute.rules | list | `[{"backendRefs":[],"matches":[{"path":{"type":"PathPrefix","value":"/"}}]}]` | HTTPRoute rules. If backendRefs is empty, traffic is forwarded to this chart's service. |
| startupProbe | object | `{"httpGet":{"path":"/","port":"http"}}` | Startup probe for the Deployment |
| livenessProbe | object | `{"httpGet":{"path":"/","port":"http"}}` | Liveness probe for the Deployment |
| readinessProbe | object | `{"httpGet":{"path":"/","port":"http"}}` | Readiness probe for the Deployment |
| resources | object | `{"limits":{"memory":"512Mi"},"requests":{"cpu":"100m","memory":"128Mi"}}` | CPU/Memory resource requests/limits |
| nodeSelector | object | `{}` | Node selector |
| tolerations | list | `[]` | Toleration labels for pod assignment |
| terminationGracePeriodSeconds | int | `30` | The terminationGracePeriodSeconds for the pod here we explicitly set the default value defined in kubernetes https://github.com/kubernetes/api/blob/d4b94f478bb2e6467873657dd7b4e1b0ac8351be/core/v1/types.go#L3114-L3118 |
| affinity | object | `{}` | The affinity constraint |
| extraVolumes | string | `nil` | Extra Volumes for the pod |
| extraVolumeMounts | string | `nil` | Extra Volume Mounts for the node-red pod |
| settings | object | `{}` | You can configure node-red using a settings file. default: {} |
| podLabels | object | `{}` | Labels to add to the node-red pod. default: {} |
| priorityClassName | string | `""` | Priority class name for the node-red pod. default: "" |
| extraSidecars | list | `[]` | You can configure extra sidecars containers to run alongside the node-red pod. default: [] |
| clusterRoleRules.enabled | bool | `false` | Enable custom rules for the application controller's ClusterRole resource default: false |
| clusterRoleRules.rules | list | `[]` | List of custom rules for the application controller's ClusterRole resource default: [] |
| sidecar.enabled | bool | `false` | Enable the sidecar |
| sidecar.env.sleep_time_sidecar | string | `"5s"` | Set the sleep time for refresh script |
| sidecar.env.method | string | `"watch"` | If METHOD is set to LIST, the sidecar will just list config-maps/secrets and exit. With SLEEP it will list all config-maps/secrets, then sleep for SLEEP_TIME seconds. Anything else will continuously watch for changes (see https://kubernetes.io/docs/reference/using-api/api-concepts/#efficient-detection-of-changes). |
| sidecar.env.label | string | `"node-red-settings"` | Label that should be used for filtering |
| sidecar.env.label_value | string | `"1"` | The value for the label you want to filter your resources on. Don't set a value to filter by any value |
| sidecar.env.script | string | `"flow_refresh.py"` | Absolute path to shell script to execute after a configmap got reloaded. |
| sidecar.env.username | string | `""` |  |
| sidecar.env.password | string | `""` | Password as key value pair |
| sidecar.env.passwordFromExistingSecret | object | `{}` | Password from existing secret |
| sidecar.env.skip_init | bool | `false` | Skip the initial request to REQ_URL when using watch mode (v2.1.0+) |
| sidecar.env.url | string | `""` | Optional: Custom target URL for the sidecar. If left empty, the internal service cluster URL is used automatically. |
| sidecar.extraNodeModules | list | `[]` | Extra Node-Modules that will be installed  from the sidecar script |
| sidecar.extraEnv | list | `[]` | Extra Environments for the sidecar |
| sidecar.resources | object | `{}` | Resources for the sidecar |
| sidecar.securityContext | object | `{}` | Security context for the sidecar |
| sidecar.livenessProbe | object | `{"httpGet":{"path":"/healthz","port":8080},"initialDelaySeconds":5,"periodSeconds":10}` | Liveness probe for the sidecar (k8s-sidecar v2+ exposes /healthz on port 8080) |
| sidecar.readinessProbe | object | `{"httpGet":{"path":"/healthz","port":8080},"initialDelaySeconds":5,"periodSeconds":10}` | Readiness probe for the sidecar (reports ready after initial sync completes) |
| sidecar.image.registry | string | `"quay.io"` | The image registry to pull the sidecar from |
| sidecar.image.repository | string | `"kiwigrid/k8s-sidecar"` | The image repository to pull from |
| sidecar.image.tag | string | `"2.14.1"` | The image tag to pull, default: `2.5.0` |
| sidecar.image.pullPolicy | string | `"IfNotPresent"` | The image pull policy, default: `IfNotPresent` |
| sidecar.volumeMounts | list | `[]` | The extra volume mounts for the sidecar |
