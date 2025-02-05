# unifi

![Version: 0.2.11](https://img.shields.io/badge/Version-0.2.11-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v9.0.114](https://img.shields.io/badge/AppVersion-v9.0.114-informational?style=flat-square)

Unifi chart for Kubernetes

**Homepage:** <https://github.com/k8sonlab/publiccharts/tree/main/charts/unifi>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicaCount | int | `1` |  |
| image.repository | string | `"jacobalberty/unifi"` | set image: use the truecharts image |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| upgradeStrategy | string | `"Recreate"` | Upgrade strategy set to recreate (no support for multiple pods) |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.name | string | `""` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| securityContext | object | `{}` |  |
| healthchecks | object | `{"livenessProbe":{"failureThreshold":5,"httpGet":{"path":"/manage/account/login","port":8443,"scheme":"HTTPS"},"initialDelaySeconds":45,"periodSeconds":15,"successThreshold":1,"timeoutSeconds":2},"readinessProbe":{"failureThreshold":3,"httpGet":{"path":"/manage/account/login","port":8443,"scheme":"HTTPS"},"initialDelaySeconds":10,"periodSeconds":15,"successThreshold":1,"timeoutSeconds":2},"startupProbe":{"failureThreshold":20,"httpGet":{"path":"/manage/account/login","port":8443,"scheme":"HTTPS"},"initialDelaySeconds":45,"periodSeconds":5,"successThreshold":1,"timeoutSeconds":2}}` | Setup liveness probes for deployment |
| service | object | `{"port":8443,"type":"ClusterIP"}` | the main Service (used for ingress) |
| serviceAP | object | `{"annotations":{},"ports":{"controller":{"number":8080,"protocol":"TCP"},"discovery":{"number":10001,"protocol":"TCP"},"stun":{"number":3478,"protocol":"UDP"}},"type":"LoadBalancer"}` | Requires load balancer, to expose the Unifi stun and discovery |
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[],"tls":[]}` | Ingress |
| resources | object | `{}` | proposed resources set under this config |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |
| environmentVars | object | `{"S6_READ_ONLY_ROOT":"1","TZ":"UTC","UMASK":"2","UMASK_SET":"2"}` | deployment environment vars (key,value style) |
| configVolume | object | `{"accessModes":["ReadWriteOnce"],"size":"10Gi","storageClassName":""}` | configVolume |
| configVolume.accessModes | list | `["ReadWriteOnce"]` | Access mode for volumes |
| configVolume.size | string | `"10Gi"` | Size of volume |

