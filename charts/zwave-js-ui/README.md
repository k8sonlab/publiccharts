# zwave-js-ui

![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 8.6.2](https://img.shields.io/badge/AppVersion-8.6.2-informational?style=flat-square)

Helmchart for zwave-js-ui

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicaCount | int | `1` |  |
| image.repository | string | `"zwavejs/zwave-js-ui"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| health | object | `{"livenessProbe":{"initialDelaySeconds":15,"path":"/health","periodSeconds":30},"readinessProbe":{"initialDelaySeconds":5,"path":"/health","periodSeconds":30},"startupProbe":{"initialDelaySeconds":5,"path":"/health","periodSeconds":30}}` | configure Probes |
| ports | object | `{"ui":{"containerPort":8091,"name":"http_ui","protocol":"TCP","servicePort":80},"websocket":{"containerPort":3000,"name":"http_websocket","protocl":"TCP","servicePort":3000}}` | ui and websocet ports |
| service.type | string | `"ClusterIP"` |  |
| strategy | object | `{"type":"Recreate"}` | Setting default strategy, to avoid running 2 containers with one stick |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.name | string | `""` |  |
| env | list | `[{"name":"ZWAVE_JS_EXTERNAL_CONFIG","value":"/usr/src/app/store/.config-db"}]` | add your env variables here, following standard syntax |
| envFrom | list | `[]` | you can add secrets and configmaps. this way you support external secrets for secure variables |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| securityContext | object | `{}` |  |
| persistence.enabled | bool | `false` | enable persistent volume, otherwise use empty dir |
| persistence.mountPath | string | `"/usr/src/app/store"` | change the path of store. Just in case you use different env variable. |
| ingress.enabled | bool | `false` |  |
| ingress.className | string | `""` |  |
| ingress.annotations | object | `{}` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| resources | object | `{"limits":{"cpu":"300m","memory":"256Mi"},"requests":{"cpu":"200m","memory":"192Mi"}}` | Initial resources, based on a 40node network |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |

