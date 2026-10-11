# node-red

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.1.2](https://img.shields.io/badge/AppVersion-4.1.2-informational?style=flat-square)
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
| deploymentStrategy | string | `""` | Deployment strategy used to replace old Pods with new ones. Defaults to `RollingUpdate`. |
| image.registry | string | `"docker.io"` | Registry for the container image. |
| image.repository | string | `"nodered/node-red"` | Repository for the container image. |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy. |
| image.tag | string | `""` | Image tag to pull. Defaults to `Chart.appVersion`. |
| rbac.enabled | bool | `true` |  |
| rbac.createClusterRole | bool | `false` | Create a ClusterRole for the Node-RED pod. Defaults to false. |
| imagePullSecrets | string | `""` | Additional image pull secrets. |
| nameOverride | string | `""` | Override the release name for the chart. |
| fullnameOverride | string | `""` | Fully override the generated name. |
| npmrc.enabled | bool | `false` | Enable custom npmrc configuration. |
| npmrc.registry | string | `"https://registry.npmjs.org"` | Registry to use for npm packages. |
| npmrc.content | string | `"# Custom npmrc config\n"` | Custom npmrc content to add. |
| env | list | `[]` | Additional environment variables for Node-RED. See the Node-RED documentation for supported values. |
| projectMode | object | `{"enabled":false}` | Enable Node-RED project mode for Git integration and project management. Note: Project mode requires write access to the /data directory and may require additional security context adjustments depending on your cluster's policies. |
| envFrom | list | `[]` |  |
| serviceAccount.create | bool | `true` | Create a service account for the workload. |
| serviceAccount.annotations | object | `{}` | Additional annotations for the service account. |
| serviceAccount.name | string | `""` | Name of the service account to use. |
| podAnnotations | object | `{}` | Additional annotations for the pod. |
| deploymentAnnotations | object | `{}` | Additional annotations for the deployment. |
| podSecurityContext | object | `{"fsGroup":1000,"runAsUser":1000}` | Pod security context for the workload. See [values.yaml](values.yaml). |
| podSecurityContext.fsGroup | int | `1000` | File system group for the pod. Defaults to 1000. |
| podSecurityContext.runAsUser | int | `1000` | User ID for the pod. Defaults to 1000. |
| securityContext | object | `{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"privileged":false,"readOnlyRootFilesystem":false,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000,"seccompProfile":{"type":"RuntimeDefault"}}` | Security context for the container. See [values.yaml](values.yaml). |
| service.type | string | `"ClusterIP"` | Kubernetes service type. |
| service.port | int | `1880` | Port exposed by the service. |
| service.annotations | object | `{}` | Annotations for the service. |
| metrics.enabled | bool | `false` | Enable the metrics service. |
| metrics.path | string | `"/metrics"` |  |
| metrics.serviceMonitor.enabled | bool | `false` | Enable a Prometheus ServiceMonitor. |
| metrics.serviceMonitor.basicAuth | object | `{}` | Basic auth configuration for the ServiceMonitor endpoint. |
| metrics.serviceMonitor.interval | string | `"30s"` | Interval between Prometheus scrapes. |
| metrics.serviceMonitor.relabelings | list | `[]` | Relabeling rules to apply to scraped samples before they are ingested. |
| metrics.serviceMonitor.metricRelabelings | list | `[]` | Metric relabeling rules to apply before ingestion. |
| metrics.serviceMonitor.selector | object | `{}` | Selector used by the ServiceMonitor. |
| metrics.serviceMonitor.namespace | string | `""` | Namespace for the ServiceMonitor. |
| metrics.serviceMonitor.additionalLabels | object | `{}` | Additional labels for the ServiceMonitor. |
| persistence.enabled | bool | `false` | Enable persistent storage for Node-RED data. |
| persistence.accessMode | string | `"ReadWriteOnce"` | Access mode for the persistent volume claim. |
| persistence.size | string | `"5Gi"` | Size of the persistent volume claim. |
| persistence.keepPVC | bool | `false` | Retain the created PVC when uninstalling the chart. Defaults to false. |
| initContainers | list | `[]` | Init containers to run before the application container starts. |
| ingress.enabled | bool | `false` | Enable the ingress resource. |
| ingress.className | string | `""` | Ingress controller class to use. |
| ingress.annotations | object | `{}` | Additional ingress annotations. |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0] | object | `{"path":"/","pathType":"ImplementationSpecific"}` | Base path for the ingress rule. |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` | Path type for the ingress rule. |
| ingress.tls | list | `[]` | TLS configuration for the ingress. |
| httpRoute.enabled | bool | `false` | Enable an HTTPRoute resource for the server. |
| httpRoute.annotations | object | `{}` | Additional annotations for the HTTPRoute. |
| httpRoute.parentRefs | list | `[]` | Parent references for Gateway API attachment. |
| httpRoute.hostnames | list | `[]` | Hostnames exposed by the HTTPRoute. |
| httpRoute.rules | list | `[{"backendRefs":[],"matches":[{"path":{"type":"PathPrefix","value":"/"}}]}]` | Rules for forwarding traffic. If backendRefs is empty, traffic is sent to this chart's service. |
| startupProbe | object | `{"httpGet":{"path":"/","port":"http"}}` | Startup probe for the deployment. |
| livenessProbe | object | `{"httpGet":{"path":"/","port":"http"}}` | Liveness probe for the deployment. |
| readinessProbe | object | `{"httpGet":{"path":"/","port":"http"}}` | Readiness probe for the deployment. |
| resources | object | `{"limits":{"memory":"512Mi"},"requests":{"cpu":"100m","memory":"128Mi"}}` | CPU and memory requests and limits for the pod. |
| nodeSelector | object | `{}` | Node selector labels for pod assignment. |
| tolerations | list | `[]` | Tolerations for pod assignment. |
| terminationGracePeriodSeconds | int | `30` | Grace period before terminating the pod. This value is explicitly set to the Kubernetes default. https://github.com/kubernetes/api/blob/d4b94f478bb2e6467873657dd7b4e1b0ac8351be/core/v1/types.go#L3114-L3118 |
| affinity | object | `{}` | Affinity rules for pod scheduling. |
| extraVolumes | string | `nil` | Additional volumes to mount into the pod. |
| extraVolumeMounts | string | `nil` | Additional volume mounts for the Node-RED pod. |
| settings | object | `{}` | Configuration for the Node-RED settings file. Defaults to {}. |
| podLabels | object | `{}` | Additional labels to add to the pod. Defaults to {}. |
| priorityClassName | string | `""` | Priority class name for the pod. Defaults to empty. |
| extraSidecars | list | `[]` | Additional sidecars to run alongside the Node-RED container. Defaults to []. |
| clusterRoleRules.enabled | bool | `false` | Enable custom rules for the application controller's ClusterRole resource. Defaults to false. |
| clusterRoleRules.rules | list | `[]` | List of custom rules for the application controller's ClusterRole resource. Defaults to []. |
| sidecar.enabled | bool | `false` | Enable the sidecar. |
| sidecar.env.sleep_time_sidecar | string | `"5s"` | Sleep interval for the refresh script. |
| sidecar.env.method | string | `"watch"` | If METHOD is set to LIST, the sidecar lists ConfigMaps and Secrets and exits. With SLEEP, it lists all ConfigMaps and Secrets, waits for the configured duration, and then repeats. Any other value keeps watching for changes. |
| sidecar.env.label | string | `"node-red-settings"` | Label used to filter watched resources. |
| sidecar.env.label_value | string | `"1"` | Label value used to filter watched resources. Leave empty to match any value. |
| sidecar.env.script | string | `"flow_refresh.py"` | Absolute path to the shell script to execute after a ConfigMap is reloaded. |
| sidecar.env.username | string | `""` |  |
| sidecar.env.password | string | `""` | Password as a key/value pair. |
| sidecar.env.passwordFromExistingSecret | object | `{}` | Password from an existing secret. |
| sidecar.env.skip_init | bool | `false` | Skip the initial request to REQ_URL when using watch mode (v2.1.0+). |
| sidecar.env.url | string | `""` | Optional custom target URL for the sidecar. If empty, the in-cluster service URL is used automatically. |
| sidecar.extraNodeModules | list | `[]` | Extra Node modules to install from the sidecar script. |
| sidecar.extraEnv | list | `[]` | Extra environment variables for the sidecar. |
| sidecar.resources | object | `{}` | Resources for the sidecar. |
| sidecar.securityContext | object | `{}` | Security context for the sidecar. |
| sidecar.livenessProbe | object | `{"httpGet":{"path":"/healthz","port":8080},"initialDelaySeconds":5,"periodSeconds":10}` | Liveness probe for the sidecar. k8s-sidecar v2+ exposes /healthz on port 8080. |
| sidecar.readinessProbe | object | `{"httpGet":{"path":"/healthz","port":8080},"initialDelaySeconds":5,"periodSeconds":10}` | Readiness probe for the sidecar. Reports ready after the initial sync completes. |
| sidecar.image.registry | string | `"quay.io"` | Registry for the sidecar image. |
| sidecar.image.repository | string | `"kiwigrid/k8s-sidecar"` | Repository for the sidecar image. |
| sidecar.image.tag | string | `"2.5.0"` | Image tag to pull. Defaults to `2.5.0`. |
| sidecar.image.pullPolicy | string | `"IfNotPresent"` | Image pull policy. Defaults to `IfNotPresent`. |
| sidecar.volumeMounts | list | `[]` | Extra volume mounts for the sidecar. |
