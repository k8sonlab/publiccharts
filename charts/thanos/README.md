# thanos

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.30.2](https://img.shields.io/badge/AppVersion-0.30.2-informational?style=flat-square)

Helm chart for Thanos.
Based on https://artifacthub.io/packages/helm/stevehipwell/thanos

**Homepage:** <https://thanos.io/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Vassilis Aretakis |  | <https://github.com/varet80> |

## Source Code

* <https://github.com/thanos-io/thanos>
* <https://github.com/thanos-io/kube-thanos>
* <https://github.com/k8sonlab/publiccharts>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additionalEndpoints | list | `[]` |  |
| additionalReplicaLabels | list | `[]` |  |
| commonLabels | object | `{}` |  |
| compact.affinity | object | `{}` |  |
| compact.enabled | bool | `false` |  |
| compact.extraArgs | list | `[]` |  |
| compact.extraEnv | list | `[]` |  |
| compact.livenessProbe.failureThreshold | int | `4` |  |
| compact.livenessProbe.httpGet.path | string | `"/-/healthy"` |  |
| compact.livenessProbe.httpGet.port | string | `"http"` |  |
| compact.livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| compact.livenessProbe.initialDelaySeconds | int | `0` |  |
| compact.livenessProbe.periodSeconds | int | `30` |  |
| compact.livenessProbe.successThreshold | int | `1` |  |
| compact.livenessProbe.timeoutSeconds | int | `1` |  |
| compact.nodeSelector | object | `{}` |  |
| compact.persistence.accessMode | string | `"ReadWriteOnce"` |  |
| compact.persistence.annotations | object | `{}` |  |
| compact.persistence.enabled | bool | `false` |  |
| compact.persistence.existingClaim | string | `""` |  |
| compact.persistence.size | string | `"8Gi"` |  |
| compact.persistence.storageClass | string | `"standard"` |  |
| compact.podAnnotations | object | `{}` |  |
| compact.podLabels | object | `{}` |  |
| compact.podSecurityContext.fsGroup | int | `65534` |  |
| compact.podSecurityContext.runAsUser | int | `65534` |  |
| compact.priorityClassName | string | `""` |  |
| compact.readinessProbe.failureThreshold | int | `20` |  |
| compact.readinessProbe.httpGet.path | string | `"/-/ready"` |  |
| compact.readinessProbe.httpGet.port | string | `"http"` |  |
| compact.readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| compact.readinessProbe.initialDelaySeconds | int | `0` |  |
| compact.readinessProbe.periodSeconds | int | `5` |  |
| compact.readinessProbe.successThreshold | int | `1` |  |
| compact.readinessProbe.timeoutSeconds | int | `1` |  |
| compact.resources | object | `{}` |  |
| compact.securityContext | object | `{}` |  |
| compact.service.annotations | object | `{}` |  |
| compact.serviceAccount.annotations | object | `{}` |  |
| compact.serviceAccount.automountToken | bool | `false` |  |
| compact.serviceAccount.create | bool | `true` |  |
| compact.serviceAccount.labels | object | `{}` |  |
| compact.serviceAccount.name | string | `""` |  |
| compact.terminationGracePeriodSeconds | string | `nil` |  |
| compact.tolerations | list | `[]` |  |
| compact.topologySpreadConstraints | object | `{}` |  |
| compact.updateStrategy | object | `{}` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"quay.io/thanos/thanos"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| logFormat | string | `"logfmt"` |  |
| logLevel | string | `"info"` |  |
| nameOverride | string | `""` |  |
| objstoreConfig.create | bool | `true` |  |
| objstoreConfig.key | string | `"config"` |  |
| objstoreConfig.name | string | `""` |  |
| objstoreConfig.value | string | `"type: FILESYSTEM\nconfig:\n  directory: /var/thanos/store/s3"` |  |
| query.additionalStores | list | `[]` |  |
| query.affinity | object | `{}` |  |
| query.autoscaling.enabled | bool | `false` |  |
| query.autoscaling.maxReplicas | int | `3` |  |
| query.autoscaling.minReplicas | int | `1` |  |
| query.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| query.autoscaling.targetMemoryUtilizationPercentage | string | `nil` |  |
| query.extraArgs | list | `[]` |  |
| query.extraEnv | list | `[]` |  |
| query.ingress.annotations | object | `{}` |  |
| query.ingress.enabled | bool | `false` |  |
| query.ingress.hosts | list | `[]` |  |
| query.ingress.ingressClassName | string | `""` |  |
| query.ingress.path | string | `"/"` |  |
| query.ingress.tls | list | `[]` |  |
| query.livenessProbe.failureThreshold | int | `4` |  |
| query.livenessProbe.httpGet.path | string | `"/-/healthy"` |  |
| query.livenessProbe.httpGet.port | string | `"http"` |  |
| query.livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| query.livenessProbe.initialDelaySeconds | int | `0` |  |
| query.livenessProbe.periodSeconds | int | `30` |  |
| query.livenessProbe.successThreshold | int | `1` |  |
| query.livenessProbe.timeoutSeconds | int | `1` |  |
| query.nodeSelector | object | `{}` |  |
| query.podAnnotations | object | `{}` |  |
| query.podDisruptionBudget.enabled | bool | `false` |  |
| query.podDisruptionBudget.maxUnavailable | string | `nil` |  |
| query.podDisruptionBudget.minAvailable | string | `nil` |  |
| query.podLabels | object | `{}` |  |
| query.podSecurityContext.fsGroup | int | `65534` |  |
| query.podSecurityContext.runAsUser | int | `65534` |  |
| query.priorityClassName | string | `""` |  |
| query.readinessProbe.failureThreshold | int | `20` |  |
| query.readinessProbe.httpGet.path | string | `"/-/ready"` |  |
| query.readinessProbe.httpGet.port | string | `"http"` |  |
| query.readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| query.readinessProbe.initialDelaySeconds | int | `0` |  |
| query.readinessProbe.periodSeconds | int | `5` |  |
| query.readinessProbe.successThreshold | int | `1` |  |
| query.readinessProbe.timeoutSeconds | int | `1` |  |
| query.replicaLabels | list | `[]` |  |
| query.replicas | int | `1` |  |
| query.resources | object | `{}` |  |
| query.securityContext | object | `{}` |  |
| query.service.annotations | object | `{}` |  |
| query.serviceAccount.annotations | object | `{}` |  |
| query.serviceAccount.automountToken | bool | `false` |  |
| query.serviceAccount.create | bool | `true` |  |
| query.serviceAccount.labels | object | `{}` |  |
| query.serviceAccount.name | string | `""` |  |
| query.terminationGracePeriodSeconds | string | `nil` |  |
| query.tolerations | list | `[]` |  |
| query.topologySpreadConstraints | object | `{}` |  |
| query.updateStrategy | object | `{}` |  |
| queryFrontend.affinity | object | `{}` |  |
| queryFrontend.autoscaling.enabled | bool | `false` |  |
| queryFrontend.autoscaling.maxReplicas | int | `3` |  |
| queryFrontend.autoscaling.minReplicas | int | `1` |  |
| queryFrontend.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| queryFrontend.autoscaling.targetMemoryUtilizationPercentage | string | `nil` |  |
| queryFrontend.enabled | bool | `false` |  |
| queryFrontend.extraArgs | list | `[]` |  |
| queryFrontend.extraEnv | list | `[]` |  |
| queryFrontend.ingress.annotations | object | `{}` |  |
| queryFrontend.ingress.enabled | bool | `false` |  |
| queryFrontend.ingress.hosts | list | `[]` |  |
| queryFrontend.ingress.ingressClassName | string | `""` |  |
| queryFrontend.ingress.path | string | `"/"` |  |
| queryFrontend.ingress.tls | list | `[]` |  |
| queryFrontend.livenessProbe.failureThreshold | int | `4` |  |
| queryFrontend.livenessProbe.httpGet.path | string | `"/-/healthy"` |  |
| queryFrontend.livenessProbe.httpGet.port | string | `"http"` |  |
| queryFrontend.livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| queryFrontend.livenessProbe.initialDelaySeconds | int | `0` |  |
| queryFrontend.livenessProbe.periodSeconds | int | `30` |  |
| queryFrontend.livenessProbe.successThreshold | int | `1` |  |
| queryFrontend.livenessProbe.timeoutSeconds | int | `1` |  |
| queryFrontend.nodeSelector | object | `{}` |  |
| queryFrontend.podAnnotations | object | `{}` |  |
| queryFrontend.podDisruptionBudget.enabled | bool | `false` |  |
| queryFrontend.podDisruptionBudget.maxUnavailable | string | `nil` |  |
| queryFrontend.podDisruptionBudget.minAvailable | string | `nil` |  |
| queryFrontend.podLabels | object | `{}` |  |
| queryFrontend.podSecurityContext.fsGroup | int | `65534` |  |
| queryFrontend.podSecurityContext.runAsUser | int | `65534` |  |
| queryFrontend.priorityClassName | string | `""` |  |
| queryFrontend.readinessProbe.failureThreshold | int | `20` |  |
| queryFrontend.readinessProbe.httpGet.path | string | `"/-/ready"` |  |
| queryFrontend.readinessProbe.httpGet.port | string | `"http"` |  |
| queryFrontend.readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| queryFrontend.readinessProbe.initialDelaySeconds | int | `0` |  |
| queryFrontend.readinessProbe.periodSeconds | int | `5` |  |
| queryFrontend.readinessProbe.successThreshold | int | `1` |  |
| queryFrontend.readinessProbe.timeoutSeconds | int | `1` |  |
| queryFrontend.replicas | int | `1` |  |
| queryFrontend.resources | object | `{}` |  |
| queryFrontend.securityContext | object | `{}` |  |
| queryFrontend.service.annotations | object | `{}` |  |
| queryFrontend.serviceAccount.annotations | object | `{}` |  |
| queryFrontend.serviceAccount.automountToken | bool | `false` |  |
| queryFrontend.serviceAccount.create | bool | `true` |  |
| queryFrontend.serviceAccount.labels | object | `{}` |  |
| queryFrontend.serviceAccount.name | string | `""` |  |
| queryFrontend.terminationGracePeriodSeconds | string | `nil` |  |
| queryFrontend.tolerations | list | `[]` |  |
| queryFrontend.topologySpreadConstraints | object | `{}` |  |
| queryFrontend.updateStrategy | object | `{}` |  |
| receive.enabled | bool | `false` |  |
| receive.ingestor.affinity | object | `{}` |  |
| receive.ingestor.extraArgs | list | `[]` |  |
| receive.ingestor.extraEnv | list | `[]` |  |
| receive.ingestor.livenessProbe.failureThreshold | int | `8` |  |
| receive.ingestor.livenessProbe.httpGet.path | string | `"/-/healthy"` |  |
| receive.ingestor.livenessProbe.httpGet.port | string | `"http"` |  |
| receive.ingestor.livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| receive.ingestor.livenessProbe.initialDelaySeconds | int | `0` |  |
| receive.ingestor.livenessProbe.periodSeconds | int | `30` |  |
| receive.ingestor.livenessProbe.successThreshold | int | `1` |  |
| receive.ingestor.livenessProbe.timeoutSeconds | int | `1` |  |
| receive.ingestor.nodeSelector | object | `{}` |  |
| receive.ingestor.persistence.accessMode | string | `"ReadWriteOnce"` |  |
| receive.ingestor.persistence.annotations | object | `{}` |  |
| receive.ingestor.persistence.enabled | bool | `false` |  |
| receive.ingestor.persistence.existingClaim | string | `""` |  |
| receive.ingestor.persistence.size | string | `"8Gi"` |  |
| receive.ingestor.persistence.storageClass | string | `"standard"` |  |
| receive.ingestor.podAnnotations | object | `{}` |  |
| receive.ingestor.podDisruptionBudget.enabled | bool | `false` |  |
| receive.ingestor.podDisruptionBudget.maxUnavailable | string | `nil` |  |
| receive.ingestor.podDisruptionBudget.minAvailable | string | `nil` |  |
| receive.ingestor.podLabels | object | `{}` |  |
| receive.ingestor.podSecurityContext.fsGroup | int | `65534` |  |
| receive.ingestor.podSecurityContext.runAsUser | int | `65534` |  |
| receive.ingestor.priorityClassName | string | `""` |  |
| receive.ingestor.readinessProbe.failureThreshold | int | `20` |  |
| receive.ingestor.readinessProbe.httpGet.path | string | `"/-/ready"` |  |
| receive.ingestor.readinessProbe.httpGet.port | string | `"http"` |  |
| receive.ingestor.readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| receive.ingestor.readinessProbe.initialDelaySeconds | int | `0` |  |
| receive.ingestor.readinessProbe.periodSeconds | int | `5` |  |
| receive.ingestor.readinessProbe.successThreshold | int | `1` |  |
| receive.ingestor.readinessProbe.timeoutSeconds | int | `1` |  |
| receive.ingestor.replicas | int | `1` |  |
| receive.ingestor.resources | object | `{}` |  |
| receive.ingestor.securityContext | object | `{}` |  |
| receive.ingestor.service.annotations | object | `{}` |  |
| receive.ingestor.serviceAccount.annotations | object | `{}` |  |
| receive.ingestor.serviceAccount.automountToken | bool | `false` |  |
| receive.ingestor.serviceAccount.create | bool | `true` |  |
| receive.ingestor.serviceAccount.labels | object | `{}` |  |
| receive.ingestor.serviceAccount.name | string | `""` |  |
| receive.ingestor.terminationGracePeriodSeconds | string | `nil` |  |
| receive.ingestor.tolerations | list | `[]` |  |
| receive.ingestor.topologySpreadConstraints | object | `{}` |  |
| receive.ingestor.updateStrategy | object | `{}` |  |
| receive.replicationFactor | int | `1` |  |
| receive.retention | string | `"48h"` |  |
| receive.router.affinity | object | `{}` |  |
| receive.router.autoscaling.enabled | bool | `false` |  |
| receive.router.autoscaling.maxReplicas | int | `3` |  |
| receive.router.autoscaling.minReplicas | int | `1` |  |
| receive.router.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| receive.router.autoscaling.targetMemoryUtilizationPercentage | string | `nil` |  |
| receive.router.enabled | bool | `true` |  |
| receive.router.extraArgs | list | `[]` |  |
| receive.router.extraEnv | list | `[]` |  |
| receive.router.ingress.annotations | object | `{}` |  |
| receive.router.ingress.enabled | bool | `false` |  |
| receive.router.ingress.hosts | list | `[]` |  |
| receive.router.ingress.ingressClassName | string | `""` |  |
| receive.router.ingress.path | string | `"/"` |  |
| receive.router.ingress.tls | list | `[]` |  |
| receive.router.livenessProbe.failureThreshold | int | `4` |  |
| receive.router.livenessProbe.httpGet.path | string | `"/-/healthy"` |  |
| receive.router.livenessProbe.httpGet.port | string | `"http"` |  |
| receive.router.livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| receive.router.livenessProbe.initialDelaySeconds | int | `0` |  |
| receive.router.livenessProbe.periodSeconds | int | `30` |  |
| receive.router.livenessProbe.successThreshold | int | `1` |  |
| receive.router.livenessProbe.timeoutSeconds | int | `1` |  |
| receive.router.nodeSelector | object | `{}` |  |
| receive.router.podAnnotations | object | `{}` |  |
| receive.router.podDisruptionBudget.enabled | bool | `false` |  |
| receive.router.podDisruptionBudget.maxUnavailable | string | `nil` |  |
| receive.router.podDisruptionBudget.minAvailable | string | `nil` |  |
| receive.router.podLabels | object | `{}` |  |
| receive.router.podSecurityContext.fsGroup | int | `65534` |  |
| receive.router.podSecurityContext.runAsUser | int | `65534` |  |
| receive.router.priorityClassName | string | `""` |  |
| receive.router.readinessProbe.failureThreshold | int | `20` |  |
| receive.router.readinessProbe.httpGet.path | string | `"/-/ready"` |  |
| receive.router.readinessProbe.httpGet.port | string | `"http"` |  |
| receive.router.readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| receive.router.readinessProbe.initialDelaySeconds | int | `0` |  |
| receive.router.readinessProbe.periodSeconds | int | `5` |  |
| receive.router.readinessProbe.successThreshold | int | `1` |  |
| receive.router.readinessProbe.timeoutSeconds | int | `1` |  |
| receive.router.replicas | int | `1` |  |
| receive.router.resources | object | `{}` |  |
| receive.router.securityContext | object | `{}` |  |
| receive.router.service.annotations | object | `{}` |  |
| receive.router.serviceAccount.annotations | object | `{}` |  |
| receive.router.serviceAccount.automountToken | bool | `false` |  |
| receive.router.serviceAccount.create | bool | `true` |  |
| receive.router.serviceAccount.labels | object | `{}` |  |
| receive.router.serviceAccount.name | string | `""` |  |
| receive.router.terminationGracePeriodSeconds | string | `nil` |  |
| receive.router.tolerations | list | `[]` |  |
| receive.router.topologySpreadConstraints | object | `{}` |  |
| receive.router.updateStrategy | object | `{}` |  |
| rule.affinity | object | `{}` |  |
| rule.alertmanagersConfig.create | bool | `true` |  |
| rule.alertmanagersConfig.key | string | `"config"` |  |
| rule.alertmanagersConfig.name | string | `""` |  |
| rule.alertmanagersConfig.value | string | `"alertmanagers: []"` |  |
| rule.blockDuration | string | `"2h"` |  |
| rule.configReloader.enabled | bool | `true` |  |
| rule.configReloader.resources | object | `{}` |  |
| rule.enabled | bool | `false` |  |
| rule.evalInterval | string | `"1m"` |  |
| rule.extraArgs | list | `[]` |  |
| rule.extraEnv | list | `[]` |  |
| rule.ingress.annotations | object | `{}` |  |
| rule.ingress.enabled | bool | `false` |  |
| rule.ingress.hosts | list | `[]` |  |
| rule.ingress.ingressClassName | string | `""` |  |
| rule.ingress.path | string | `"/"` |  |
| rule.ingress.tls | list | `[]` |  |
| rule.livenessProbe.failureThreshold | int | `8` |  |
| rule.livenessProbe.httpGet.path | string | `"/-/healthy"` |  |
| rule.livenessProbe.httpGet.port | string | `"http"` |  |
| rule.livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| rule.livenessProbe.initialDelaySeconds | int | `0` |  |
| rule.livenessProbe.periodSeconds | int | `30` |  |
| rule.livenessProbe.successThreshold | int | `1` |  |
| rule.livenessProbe.timeoutSeconds | int | `1` |  |
| rule.nodeSelector | object | `{}` |  |
| rule.persistence.accessMode | string | `"ReadWriteOnce"` |  |
| rule.persistence.annotations | object | `{}` |  |
| rule.persistence.enabled | bool | `false` |  |
| rule.persistence.existingClaim | string | `""` |  |
| rule.persistence.size | string | `"8Gi"` |  |
| rule.persistence.storageClass | string | `"standard"` |  |
| rule.podAnnotations | object | `{}` |  |
| rule.podDisruptionBudget.enabled | bool | `false` |  |
| rule.podDisruptionBudget.maxUnavailable | string | `nil` |  |
| rule.podDisruptionBudget.minAvailable | string | `nil` |  |
| rule.podLabels | object | `{}` |  |
| rule.podSecurityContext.fsGroup | int | `65534` |  |
| rule.podSecurityContext.runAsUser | int | `65534` |  |
| rule.priorityClassName | string | `""` |  |
| rule.readinessProbe.failureThreshold | int | `20` |  |
| rule.readinessProbe.httpGet.path | string | `"/-/ready"` |  |
| rule.readinessProbe.httpGet.port | string | `"http"` |  |
| rule.readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| rule.readinessProbe.initialDelaySeconds | int | `0` |  |
| rule.readinessProbe.periodSeconds | int | `5` |  |
| rule.readinessProbe.successThreshold | int | `1` |  |
| rule.readinessProbe.timeoutSeconds | int | `1` |  |
| rule.replicas | int | `1` |  |
| rule.resources | object | `{}` |  |
| rule.retention | string | `"48h"` |  |
| rule.rules.create | bool | `true` |  |
| rule.rules.name | string | `""` |  |
| rule.rules.value | string | `""` |  |
| rule.securityContext | object | `{}` |  |
| rule.service.annotations | object | `{}` |  |
| rule.serviceAccount.annotations | object | `{}` |  |
| rule.serviceAccount.automountToken | bool | `false` |  |
| rule.serviceAccount.create | bool | `true` |  |
| rule.serviceAccount.labels | object | `{}` |  |
| rule.serviceAccount.name | string | `""` |  |
| rule.terminationGracePeriodSeconds | string | `nil` |  |
| rule.tolerations | list | `[]` |  |
| rule.topologySpreadConstraints | object | `{}` |  |
| rule.updateStrategy | object | `{}` |  |
| serviceMonitor.additionalLabels | object | `{}` |  |
| serviceMonitor.enabled | bool | `false` |  |
| serviceMonitor.endpointConfig | object | `{}` |  |
| serviceMonitor.interval | string | `nil` |  |
| storeGateway.affinity | object | `{}` |  |
| storeGateway.extraArgs | list | `[]` |  |
| storeGateway.extraEnv | list | `[]` |  |
| storeGateway.livenessProbe.failureThreshold | int | `8` |  |
| storeGateway.livenessProbe.httpGet.path | string | `"/-/healthy"` |  |
| storeGateway.livenessProbe.httpGet.port | string | `"http"` |  |
| storeGateway.livenessProbe.httpGet.scheme | string | `"HTTP"` |  |
| storeGateway.livenessProbe.initialDelaySeconds | int | `0` |  |
| storeGateway.livenessProbe.periodSeconds | int | `30` |  |
| storeGateway.livenessProbe.successThreshold | int | `1` |  |
| storeGateway.livenessProbe.timeoutSeconds | int | `1` |  |
| storeGateway.nodeSelector | object | `{}` |  |
| storeGateway.persistence.accessMode | string | `"ReadWriteOnce"` |  |
| storeGateway.persistence.annotations | object | `{}` |  |
| storeGateway.persistence.enabled | bool | `false` |  |
| storeGateway.persistence.existingClaim | string | `""` |  |
| storeGateway.persistence.size | string | `"8Gi"` |  |
| storeGateway.persistence.storageClass | string | `"standard"` |  |
| storeGateway.podAnnotations | object | `{}` |  |
| storeGateway.podDisruptionBudget.enabled | bool | `false` |  |
| storeGateway.podDisruptionBudget.maxUnavailable | string | `nil` |  |
| storeGateway.podDisruptionBudget.minAvailable | string | `nil` |  |
| storeGateway.podLabels | object | `{}` |  |
| storeGateway.podSecurityContext.fsGroup | int | `65534` |  |
| storeGateway.podSecurityContext.runAsUser | int | `65534` |  |
| storeGateway.priorityClassName | string | `""` |  |
| storeGateway.readinessProbe.failureThreshold | int | `20` |  |
| storeGateway.readinessProbe.httpGet.path | string | `"/-/ready"` |  |
| storeGateway.readinessProbe.httpGet.port | string | `"http"` |  |
| storeGateway.readinessProbe.httpGet.scheme | string | `"HTTP"` |  |
| storeGateway.readinessProbe.initialDelaySeconds | int | `0` |  |
| storeGateway.readinessProbe.periodSeconds | int | `5` |  |
| storeGateway.readinessProbe.successThreshold | int | `1` |  |
| storeGateway.readinessProbe.timeoutSeconds | int | `1` |  |
| storeGateway.replicas | int | `1` |  |
| storeGateway.resources | object | `{}` |  |
| storeGateway.securityContext | object | `{}` |  |
| storeGateway.service.annotations | object | `{}` |  |
| storeGateway.serviceAccount.annotations | object | `{}` |  |
| storeGateway.serviceAccount.automountToken | bool | `false` |  |
| storeGateway.serviceAccount.create | bool | `true` |  |
| storeGateway.serviceAccount.labels | object | `{}` |  |
| storeGateway.serviceAccount.name | string | `""` |  |
| storeGateway.terminationGracePeriodSeconds | string | `nil` |  |
| storeGateway.tolerations | list | `[]` |  |
| storeGateway.topologySpreadConstraints | object | `{}` |  |
| storeGateway.updateStrategy | object | `{}` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)