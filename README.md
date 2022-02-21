# did-auth-proxy-helm

![Version: 0.0.4](https://img.shields.io/badge/Version-0.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.4](https://img.shields.io/badge/AppVersion-0.0.4-informational?style=flat-square)

A Helm chart for DID auth proxy

**Homepage:** <https://github.com/energywebfoundation/did-auth-proxy-poc>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | nginx | 9.7.5 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| appValues.ACCEPTED_ROLES | string | `"role1.roles.app-test2.apps.artur.iam.ewc"` |  |
| appValues.CACHE_SERVER_LOGIN_PRVKEY | string | `"eab5e5ccb983fad7bf7f5cb6b475a7aea95eff0c6523291b0c0ae38b5855459c"` |  |
| appValues.JWT_SECRET | string | `"asecretstring"` |  |
| appValues.PORT | int | `80` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| config.configRefName | object | `{}` |  |
| config.enabled | bool | `false` |  |
| config.secretRefName | object | `{}` |  |
| fullnameOverride | string | `"did-auth-proxy-helm"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"098061033856.dkr.ecr.us-west-2.amazonaws.com/did-auth-proxy"` |  |
| image.tag | string | `"latest"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `"did-auth-proxy-helm"` |  |
| nodeSelector | object | `{}` |  |
| opsValues.CACHE_SERVER_URL | string | `"https://identitycache-dev.energyweb.org/v1"` |  |
| opsValues.RPC_URL | string | `"https://volta-rpc.energyweb.org/"` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| sealedSecret.annotations | object | `{}` |  |
| sealedSecret.enabled | bool | `false` |  |
| sealedSecret.encryptedData | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
