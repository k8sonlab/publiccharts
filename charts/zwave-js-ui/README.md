# zwave-js-ui

![Version: 0.5.5](https://img.shields.io/badge/Version-0.5.5-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 11.12.0](https://img.shields.io/badge/AppVersion-11.12.0-informational?style=flat-square)

Helmchart for zwave-js-ui

**Homepage:** <https://github.com/k8sonlab/publiccharts/tree/main/charts/zwave-js-ui>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| varet80 |  |  |

## Source Code

* <https://github.com/zwave-js/zwave-js-ui>
* <https://github.com/zwave-js/node-zwave-js>
* <https://github.com/k8sonlab/zwave-js-prom-exporter>

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
| health | object | `{"livenessProbe":{"httpHeaders":[{"name":"Accept","value":"text/plain"}],"initialDelaySeconds":15,"path":"/health","periodSeconds":30},"readinessProbe":{"httpHeaders":[{"name":"Accept","value":"text/plain"}],"initialDelaySeconds":5,"path":"/health","periodSeconds":30},"startupProbe":{"httpHeaders":[{"name":"Accept","value":"text/plain"}],"initialDelaySeconds":5,"path":"/health","periodSeconds":30}}` | configure Probes |
| ports | object | `{"promExporter":{"containerPort":9090,"name":"http-exporter","protocol":"TCP","servicePort":9090},"ui":{"containerPort":8091,"name":"http-ui","protocol":"TCP","servicePort":80},"websocket":{"containerPort":3000,"name":"http-websocket","protocol":"TCP","servicePort":3000}}` | ui and websocet ports |
| service.type | string | `"ClusterIP"` |  |
| service.port | int | `8091` |  |
| service.annotations | object | `{}` |  |
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
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | Support custom usb device usbDevice: /dev/ttyUSB0 |
| resources | object | `{"limits":{"cpu":"300m","memory":"256Mi"},"requests":{"cpu":"200m","memory":"192Mi"}}` | Initial resources, based on a 40node network |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |
| serviceMonitor | object | `{"labels":{},"namespaceSelector":{},"promExporter":{"enabled":true,"endpointAdditions":{},"interval":"30s"},"ui":{"enabled":false,"endpointAdditions":{},"interval":"30s"}}` | Support Prometheus ServiceMonitor |
| serviceMonitor.namespaceSelector | object | `{}` | namespace selector |
| serviceMonitor.promExporter.enabled | bool | `true` | not required, placeholder for future changes. Currently controled under promExporter.enabled |
| serviceMonitor.promExporter.interval | string | `"30s"` | interval |
| serviceMonitor.promExporter.endpointAdditions | object | `{}` | endpoint additions - add endpoint modifications |
| serviceMonitor.ui.enabled | bool | `false` | Enable Zwave-js-ui metrics endpoint pulling |
| serviceMonitor.ui.interval | string | `"30s"` | interval |
| serviceMonitor.ui.endpointAdditions | object | `{}` | endpoint additions - add endpoint modifications |
| promExporter | object | `{"enabled":false,"health":{"livenessProbe":{"initialDelaySeconds":15,"path":"/healthz","periodSeconds":30},"readinessProbe":{"initialDelaySeconds":5,"path":"/healthz","periodSeconds":30},"startupProbe":{"initialDelaySeconds":5,"path":"/healthz","periodSeconds":30}},"image":{"pullPolicy":"IfNotPresent","repository":"ghcr.io/k8sonlab/zwave-js-prom-exporter","tag":"0.2.5"},"port":9090,"resources":{"limits":{"cpu":"100m","memory":"128Mi"},"requests":{"cpu":"50m","memory":"64Mi"}}}` | Prometheus Exporter Sidecar |
| promExporter.enabled | bool | `false` | enable Prometheus Exporter sidecar |
| promExporter.port | int | `9090` | port for the exporter |
| promExporter.health | object | `{"livenessProbe":{"initialDelaySeconds":15,"path":"/healthz","periodSeconds":30},"readinessProbe":{"initialDelaySeconds":5,"path":"/healthz","periodSeconds":30},"startupProbe":{"initialDelaySeconds":5,"path":"/healthz","periodSeconds":30}}` | probes for the sidecar |
| promExporter.resources | object | `{"limits":{"cpu":"100m","memory":"128Mi"},"requests":{"cpu":"50m","memory":"64Mi"}}` | resources for the sidecar |
