# github-exporter

![Version: 0.0.4](https://img.shields.io/badge/Version-0.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v2.3.1](https://img.shields.io/badge/AppVersion-v2.3.1-informational?style=flat-square)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue)](https://opensource.org)

A Helm chart for github-exporter

**Homepage:** <https://github.com/githubexporter/github-exporter>

## Install

You can install this chart from the classic Helm repository or from OCI in GHCR.

### Helm repository

```bash
helm repo add publiccharts https://charts.ar80.eu
helm repo update
helm install my-release publiccharts/github-exporter
```

### OCI registry (GHCR)

```bash
helm registry login ghcr.io
helm install my-release oci://ghcr.io/k8sonlab/publiccharts/github-exporter --version <chart-version>
```

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| varet80 |  | <https://github.com/varet80> |
## Source Code

* <https://github.com/githubexporter/github-exporter>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicaCount | int | `1` |  |
| image.repository | string | `"githubexporter/github-exporter"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.tag | string | `nil` | Overrides the image tag. Upstream publishes Docker tags as release-<version>. |
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
| env | object | `{"FETCH_REPO_RELEASES_ENABLED":"true","GITHUB_RATE_LIMIT_ENABLED":"true","GITHUB_RESULTS_PER_PAGE":"100","LISTEN_PORT":"9171","LOG_LEVEL":"info","METRICS_PATH":"/metrics"}` | Environment variables for github-exporter. Set ORGS, REPOS, or USERS to choose what to monitor. |
| envSecretName | string | `""` | Existing secret loaded as environment variables, for example GITHUB_TOKEN or GitHub App credentials. |
| secret.create | bool | `false` | Create a secret from secret.data and load it as environment variables. |
| secret.name | string | `""` | Secret name. Defaults to the chart fullname when create is true. |
| secret.data | object | `{}` | Secret values exposed as environment variables, such as GITHUB_TOKEN. |
| service.type | string | `"ClusterIP"` |  |
| service.port | int | `9171` |  |
| probes.liveness.enabled | bool | `true` |  |
| probes.liveness.path | string | `"/"` |  |
| probes.liveness.initialDelaySeconds | int | `10` |  |
| probes.liveness.failureThreshold | int | `5` |  |
| probes.liveness.timeoutSeconds | int | `5` |  |
| probes.liveness.periodSeconds | int | `10` |  |
| probes.readiness.enabled | bool | `true` |  |
| probes.readiness.path | string | `"/metrics"` |  |
| probes.readiness.initialDelaySeconds | int | `10` |  |
| probes.readiness.failureThreshold | int | `5` |  |
| probes.readiness.timeoutSeconds | int | `5` |  |
| probes.readiness.periodSeconds | int | `20` |  |
| probes.startup.enabled | bool | `true` |  |
| probes.startup.path | string | `"/"` |  |
| probes.startup.initialDelaySeconds | int | `10` |  |
| probes.startup.failureThreshold | int | `60` |  |
| probes.startup.timeoutSeconds | int | `2` |  |
| probes.startup.periodSeconds | int | `5` |  |
| resources | object | `{}` |  |
| nodeSelector | object | `{}` |  |
| tolerations | list | `[]` |  |
| affinity | object | `{}` |  |
| extraVolumes | list | `[]` |  |
| extraVolumeMounts | list | `[]` |  |
| serviceMonitor | object | `{"enabled":false,"endpointAdditions":{},"interval":"30s","labels":{},"namespaceSelector":{}}` | Support Prometheus ServiceMonitor |
| serviceMonitor.enabled | bool | `false` | enable Service Monitor |
| serviceMonitor.labels | object | `{}` | add Custom labels, for prometheus Service Monitor |
| serviceMonitor.interval | string | `"30s"` | interval |
| serviceMonitor.namespaceSelector | object | `{}` | namespace selector |
| serviceMonitor.endpointAdditions | object | `{}` | endpoint additions - add endpoint modifications |