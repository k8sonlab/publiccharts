# cloudflared

![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2025.7.0](https://img.shields.io/badge/AppVersion-2025.7.0-informational?style=flat-square)

CloudflareD deployment for use in k8s

**Homepage:** <https://github.com/k8sonlab/publiccharts/>

## Source Code

* <https://github.com/k8sonlab/publiccharts>
* <https://github.com/cloudflare/cloudflared/>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| cloudflare | object | `{"account":"","enableDefault404":true,"enableWarp":false,"ingress":[],"secret":"","secretName":null,"tunnelId":"","tunnelName":""}` | Cloudflare parameters |
| cloudflare.account | string | `""` | Your Cloudflare account number |
| cloudflare.tunnelName | string | `""` | The name of the tunnel this instance will serve |
| cloudflare.tunnelId | string | `""` | The ID of the above tunnel |
| cloudflare.secret | string | `""` | The secret for the tunnel |
| cloudflare.secretName | string | `nil` | If defined, no secret is created for the credentials, and instead, the secret referenced is used |
| cloudflare.enableWarp | bool | `false` | If true, turn on WARP routing for TCP |
| cloudflare.ingress | list | `[]` | Define ingress rules for the tunnel See https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/configuration/configuration-file/ingress |
| cloudflare.enableDefault404 | bool | `true` | If true, enable the default 404 page. Needs to be false if you want to use a '*' wildcard rule. |
| image | object | `{"pullPolicy":"IfNotPresent","repository":"cloudflare/cloudflared","tag":""}` | The image to use |
| image.tag | string | `""` | If supplied, this overrides "appVersion" |
| replicaCount | int | `2` | The version of the image to use |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.name | string | `""` | The name of the service account to use If not set and create is true, a name is generated using the fullname template |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{"runAsNonRoot":true,"runAsUser":65532}` | Security items common to everything in the pod.  Here we require that it does not run as the user defined in the image, literally named "nonroot" |
| securityContext | object | `{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"readOnlyRootFilesystem":true}` | Security items for one container. We lock it down |
| resources | object | `{}` |  |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` | Default affinity is to spread out over nodes; use this to override |
| serviceMonitor.enabled | bool | `false` | Enable prometheus Service Monitor |

