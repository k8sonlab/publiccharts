# netio-exporter

![Version: 0.1.4](https://img.shields.io/badge/Version-0.1.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.5](https://img.shields.io/badge/AppVersion-0.0.5-informational?style=flat-square)

A Helm chart for Kubernetes

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicaCount | int | `1` |  |
| image.repository | string | `"tomsajan/netio-exporter"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| securityContext.readOnlyRootFilesystem | bool | `true` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `1000` |  |
| env | object | `{"NETIO_DEBUG":"False","NETIO_PORT":9595,"NETIO_URL":"http://192.168.0.1/netio.json"}` | env values to be set |
| service.type | string | `"ClusterIP"` |  |
| service.port | int | `9595` |  |
| resources | object | `{}` |  |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |
| serviceMonitor | object | `{"enabled":false,"endpointAdditions":{},"interval":"30s","labels":{},"namespaceSelector":{}}` | Support Prometheus ServiceMonitor |
| serviceMonitor.enabled | bool | `false` | enable Service Monitor |
| serviceMonitor.labels | object | `{}` | add Custom labels, for prometheus Service Monitor |
| serviceMonitor.interval | string | `"30s"` | interval |
| serviceMonitor.namespaceSelector | object | `{}` | namespace selector |
| serviceMonitor.endpointAdditions | object | `{}` | endpoint additions - add endpoint modifications |

