# lightstep

![Version: 2.0.21](https://img.shields.io/badge/Version-2.0.20-informational?style=flat-square) ![AppVersion: 2024-01-22_17-52-59Z](https://img.shields.io/badge/AppVersion-2024--01--22_17--52--59Z-informational?style=flat-square)

Lightstep microsatellite to collect telemetry data.

**Homepage:** <https://lightstep.com/>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.behavior | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `25` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `50` |  |
| autoscaling.targetMemoryUtilizationPercentage | int | `50` |  |
| autoscalingTemplate | list | `[]` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"lightstep/microsatellite"` |  |
| image.version | string | `"2024-01-22_17-52-59Z"` |  |
| imagePullSecrets | list | `[]` |  |
| lightstep.admin_plain_port | int | `8180` |  |
| lightstep.admin_secure_port | int | `9090` |  |
| lightstep.collector_ingestion_tags | string | `nil` |  |
| lightstep.collector_pool | string | `"my-satellite-pool"` |  |
| lightstep.collector_satellite_key_secret_key | string | `""` |  |
| lightstep.collector_satellite_key_secret_name | string | `""` |  |
| lightstep.diagnostic_port | int | `8000` |  |
| lightstep.disable_access_token_checking | bool | `false` |  |
| lightstep.grpc_plain_port | int | `8184` |  |
| lightstep.grpc_secure_port | int | `9292` |  |
| lightstep.guid | string | `nil` | defaults to pod's name using the Downward API |
| lightstep.http_plain_port | int | `8181` |  |
| lightstep.http_secure_port | int | `9191` |  |
| lightstep.max_msg_size_bytes | int | `0` | Configure max gRPC receive message size in bytes. https://pkg.go.dev/google.golang.org/grpc#MaxRecvMsgSize Defaults to the library default of 4MiB if falsy. |
| lightstep.plain_port | int | `8383` |  |
| lightstep.project_name | string | `""` | REQUIRED if `lightstep.disable_access_token_checking` is `true` |
| lightstep.sample_percent | int | `0` | Configure sampling by percentage. https://docs.lightstep.com/docs/micro-satellite-configuration-parameters#sample_percent Defaults to 0, which means unconfigured here. |
| lightstep.satelliteKey | string | `""` | REQUIRED: your Satellite Key - if not set, `lightstep.collector_satellite_key_secret_name` and `lightstep.collector_satellite_key_secret_key` must be set |
| lightstep.secure_port | int | `9393` |  |
| lightstep.tls_cert_prefix | string | `nil` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| pdbMinAvailable | int | `0` |  |
| podAnnotations."prometheus.io/port" | string | `"9102"` |  |
| podAnnotations."prometheus.io/scrape" | string | `"true"` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | int | `2` |  |
| resources.limits.memory | string | `"2Gi"` |  |
| resources.requests.cpu | int | `2` |  |
| resources.requests.memory | string | `"2Gi"` |  |
| securityContext.readOnlyRootFilesystem | bool | `true` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `1000` |  |
| service.annotations | object | `{}` |  |
| service.grpc | bool | `false` | set to true if you're using GRPC in order to deploy as a headless service for better load balancing |
| service.grpcinsecure | int | `8184` |  |
| service.httpPort | int | `8181` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.clusterRole.create | bool | `true` |  |
| serviceAccount.clusterRole.name | string | `"lightstep-node-reader"` |  |
| serviceAccount.clusterRoleBinding.create | bool | `true` |  |
| serviceAccount.clusterRoleBinding.name | string | `"lightstep-read-nodes"` |  |
| serviceAccount.clusterRoleBinding.roleRefName | string | `nil` | if not set and create is true, the `serviceAccount.clusterRole.name` is used |
| serviceAccount.clusterRoleBinding.serviceAccountName | string | `nil` | if not set and and create is true, the generated serviceAccount name is used |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `nil` | the name of the service account to use; if not set and create is true, a name is generated using the fullname template |
| serviceAccount.role.create | bool | `true` |  |
| serviceAccount.role.name | string | `"lightstep-pod-reader"` |  |
| serviceAccount.roleBinding.create | bool | `true` |  |
| serviceAccount.roleBinding.name | string | `"lightstep-read-pods"` |  |
| serviceAccount.roleBinding.roleRefName | string | `nil` | if not set and create is true, the `serviceAccount.role.name` is used |
| serviceAccount.roleBinding.serviceAccountName | string | `nil` | if not set and and create is true, the generated serviceAccount name is used |
| statsd.client_prefix | string | `"client_via_canary"` |  |
| statsd.dogStatsD | bool | `false` |  |
| statsd.dogStatsDTags | string | `"pool:us-west-1,canary:true"` |  |
| statsd.enabled | bool | `false` |  |
| statsd.export_statsd | bool | `true` |  |
| statsd.host | string | `"localhost"` |  |
| statsd.image.pullPolicy | string | `"IfNotPresent"` |  |
| statsd.image.repository | string | `"prom/statsd-exporter"` |  |
| statsd.image.tag | string | `"v0.20.0"` |  |
| statsd.port | int | `9125` |  |
| statsd.prefix | string | `"lightstep.prod.us-west-1"` |  |
| statsd.resources.limits.cpu | int | `1` |  |
| statsd.resources.limits.memory | string | `"20M"` |  |
| statsd.resources.requests.cpu | int | `1` |  |
| statsd.resources.requests.memory | string | `"15M"` |  |
| statsd.satellite_prefix | string | `"satellite-canary"` |  |
| statsd.securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| statsd.securityContext.readOnlyRootFilesystem | bool | `true` |  |
| statsd.securityContext.runAsNonRoot | bool | `true` |  |
| statsd.securityContext.runAsUser | int | `1000` |  |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
