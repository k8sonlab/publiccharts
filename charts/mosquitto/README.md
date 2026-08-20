# mosquitto

![Version: 2.7.2](https://img.shields.io/badge/Version-2.7.2-informational?style=flat-square) ![AppVersion: 2.1.2-alpine](https://img.shields.io/badge/AppVersion-2.1.2--alpine-informational?style=flat-square)

Eclipse Mosquitto is an open source message broker which implements MQTT version 5, 3.1.1 and 3.1

## Install

You can install this chart from the classic Helm repository or from OCI in GHCR.

### Helm repository

```bash
helm repo add publiccharts https://k8sonlab.github.io/publiccharts
helm repo update
helm install my-release publiccharts/<mosquitto>
```

### OCI registry (GHCR)

```bash
helm registry login ghcr.io
helm install my-release oci://ghcr.io/k8sonlab/publiccharts/<mosquitto> --version <chart-version>
```

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| varet80 |  | <https://github.com/varet80> |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicaCount | int | `1` |  |
| strategyType | string | `"Recreate"` |  |
| image.repository | string | `"eclipse-mosquitto"` |  |
| image.tag | string | `nil` | Image tag of the container. defaults to chart appVersion |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| env | object | `{}` | Environment variables for main container |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `nil` |  |
| service.type | string | `"ClusterIP"` | Service type, defaults to ClusterIP |
| service.externalTrafficPolicy | string | `"Cluster"` |  |
| service.clusterIp | string | `""` | Ability to choose the Service IP (clusterIP) |
| service.loadBalancerIP | string | `""` |  |
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
| probes.liveness.enabled | bool | `true` |  |
| probes.liveness.tcpSocketPort | string | `"mqtt"` |  |
| probes.liveness.initialDelaySeconds | int | `5` |  |
| probes.liveness.periodSeconds | int | `10` |  |
| probes.liveness.timeoutSeconds | int | `1` |  |
| probes.liveness.failureThreshold | int | `6` |  |
| probes.readiness.enabled | bool | `true` |  |
| probes.readiness.tcpSocketPort | string | `"mqtt"` |  |
| probes.readiness.initialDelaySeconds | int | `3` |  |
| probes.readiness.periodSeconds | int | `10` |  |
| probes.readiness.timeoutSeconds | int | `1` |  |
| probes.readiness.failureThreshold | int | `3` |  |
| podAnnotations | object | `{}` |  |
| configMountPath | string | `"/mosquitto/config/mosquitto.conf"` |  |
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
| monitoring.podMonitor.namespace | string | `""` |  |
| monitoring.podMonitor.labels | object | `{}` |  |
| monitoring.podMonitor.interval | string | `"15s"` |  |
| monitoring.podMonitor.path | string | `"/metrics"` |  |
| monitoring.podMonitor.bearerTokenFile | string | `""` |  |
| monitoring.podMonitor.bearerTokenSecret | object | `{}` |  |
| monitoring.sidecar.enabled | bool | `false` |  |
| monitoring.sidecar.port | int | `9234` |  |
| monitoring.sidecar.args | list | `[]` |  |
| monitoring.sidecar.envs | list | `[]` |  |
| monitoring.sidecar.image.repository | string | `"nolte/mosquitto-exporter"` |  |
| monitoring.sidecar.image.tag | string | `"v0.6.3"` |  |
| monitoring.sidecar.image.pullPolicy | string | `"IfNotPresent"` |  |
| monitoring.sidecar.resources.limits.cpu | string | `"300m"` |  |
| monitoring.sidecar.resources.limits.memory | string | `"128Mi"` |  |
| monitoring.sidecar.resources.requests.cpu | string | `"100m"` |  |
| monitoring.sidecar.resources.requests.memory | string | `"64Mi"` |  |
