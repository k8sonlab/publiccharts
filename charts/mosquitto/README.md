# mosquitto

![Version: 2.6.1](https://img.shields.io/badge/Version-2.6.1-informational?style=flat-square) ![AppVersion: 2.0.21](https://img.shields.io/badge/AppVersion-2.0.21-informational?style=flat-square)

Eclipse Mosquitto is an open source message broker which implements MQTT version 5, 3.1.1 and 3.1

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicaCount | int | `1` |  |
| strategyType | string | `"Recreate"` |  |
| image.repository | string | `"eclipse-mosquitto"` |  |
| image.tag | string | `nil` | Image tag of the container. defaults to chart appVersion |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `nil` |  |
| service.type | string | `"ClusterIP"` | Service type, defaults to ClusterIP |
| service.externalTrafficPolicy | string | `"Cluster"` |  |
| service.clusterIp | string | `""` | Ability to choose the Service IP (clusterIP) |
| service.annotations | object | `{}` |  |
| ports.mqtt.port | int | `1883` |  |
| ports.mqtt.protocol | string | `"TCP"` |  |
| ports.websocket.port | int | `9090` |  |
| ports.websocket.protocol | string | `"TCP"` |  |
| persistence.enabled | bool | `true` |  |
| persistence.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.existingClaim | string | `""` |  |
| persistence.mountPath | string | `"/mosquitto/data"` |  |
| persistence.subPath | string | `""` |  |
| persistence.size | string | `"1Gi"` |  |
| resources | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| securityContext | object | `{}` |  |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |
| authentication.passwordEntries | string | `""` |  |
| authentication.passwordFilePath | string | `"/etc/mosquitto/passwordfile"` |  |
| authorization.acls | string | `""` |  |
| authorization.aclfilePath | string | `"/etc/mosquitto/aclfile"` |  |
| existingConfigMap | string | `""` |  |
| config | string | `"persistence true\npersistence_location /mosquitto/data/\nlog_dest stdout\nlistener 1883\nlistener 9090\nprotocol websockets\n"` |  |
| extraVolumes | list | `[]` |  |
| extraVolumeMounts | list | `[]` |  |
| monitoring.podMonitor.enabled | bool | `false` |  |
| monitoring.sidecar.enabled | bool | `false` |  |
| monitoring.sidecar.port | int | `9234` |  |
| monitoring.sidecar.image.repository | string | `"nolte/mosquitto-exporter"` |  |
| monitoring.sidecar.image.tag | string | `"v0.6.3"` |  |
| monitoring.sidecar.image.pullPolicy | string | `"IfNotPresent"` |  |
| monitoring.sidecar.resources.limits.cpu | string | `"300m"` |  |
| monitoring.sidecar.resources.limits.memory | string | `"128Mi"` |  |
| monitoring.sidecar.resources.requests.cpu | string | `"100m"` |  |
| monitoring.sidecar.resources.requests.memory | string | `"64Mi"` |  |

