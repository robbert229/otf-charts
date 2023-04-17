# otf-charts

![Version: 0.2.2](https://img.shields.io/badge/Version-0.2.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.30](https://img.shields.io/badge/AppVersion-0.0.30-informational?style=flat-square)

[OTF](https://github.com/leg100/otf) helm charts.

## Instructions

```bash
helm repo add otf https://leg100.github.io/otf-charts
helm upgrade --install otf otf/otf
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| CACerts | bool | `false` | Mount CA certificates - if true then the otfd container will expect to find a configmap named 'ssl-certs' with a key named 'ca.pem', which should contain CA certificates. The CA certificates are then made available to otfd and to terraform. Allows terraform to communicate with API endpoints that use custom CA certs. |
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| database | string | `""` | Postgres connection string |
| databasePasswordFromSecret | string | `nil` | Source database password from a secret |
| databaseUsernameFromSecret | string | `nil` | Source database username from a secret |
| fullnameOverride | string | `""` |  |
| github.clientID | string | `""` |  |
| github.clientSecret | string | `""` |  |
| gitlab.clientID | string | `""` |  |
| gitlab.clientSecret | string | `""` |  |
| hostname | string | `""` | Set client-accessible hostname See [docs](https://docs.otf.ninja/config/flags/#-hostname). |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"leg100/otfd"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts | list | `[]` |  |
| ingress.path | string | `"/"` |  |
| ingress.pathType | string | `"Prefix"` |  |
| ingress.tls | list | `[]` |  |
| logHTTPRequests | bool | `false` | Log http requests. |
| logLevel | string | `"info"` | Logging verbosity: error, info, debug, or trace |
| maxConfigSize | string | `""` | Max config upload size in bytes. See [docs](https://docs.otf.ninja/config/flags/#-max-config-size). |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` | Number of otfd nodes in cluster |
| resources | object | `{}` |  |
| sandbox | bool | `false` | Enable sandboxing of terraform apply - note, this will run pods as privileged |
| secret | string | `""` | Secret string for signing urls - required. |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| serviceMonitor | object | `{"enabled":false}` | Collect prometheus metrics |
| siteAdminToken | string | `""` | Site admin token - empty string disables site admin account. See [docs](https://docs.otf.ninja/config/flags/#-site-token). |
| tolerations | list | `[]` |  |
