# did-auth-proxy-helm

![Version: 0.1.5](https://img.shields.io/badge/Version-0.1.5-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.13](https://img.shields.io/badge/AppVersion-0.0.13-informational?style=flat-square)

A Helm chart for DID auth proxy

**Homepage:** <https://github.com/energywebfoundation/did-auth-proxy-poc>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | nginx | 10.2.1 |
| https://charts.bitnami.com/bitnami | redis | 16.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| appValues.ACCEPTED_ROLES | string | `"didauthtest.roles.didauthkamil.iam.ewc"` |  |
| appValues.JWT_ACCESS_TTL | int | `3600` |  |
| appValues.JWT_REFRESH_TTL | int | `86400` |  |
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
| imagePullSecrets[0].name | string | `"regcred"` |  |
| ingress.annotations."kubernetes.io/ingress.class" | string | `"nginx"` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"did-auth-proxy-sandbox.energyweb.org"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| ingress.tls[0].hosts[0] | string | `"did-auth-proxy-sandbox.energyweb.org"` |  |
| ingress.tls[0].secretName | string | `"did-auth-proxy-secret"` |  |
| nameOverride | string | `"did-auth-proxy-helm"` |  |
| nginx.customLivenessProbe.httpGet.path | string | `"/auth"` |  |
| nginx.customLivenessProbe.httpGet.port | string | `"http"` |  |
| nginx.customReadinessProbe.httpGet.path | string | `"/auth"` |  |
| nginx.customReadinessProbe.httpGet.port | string | `"http"` |  |
| nginx.fullnameOverride | string | `"did-auth-proxy-nginx"` |  |
| nginx.ingress.annotations."appgw.ingress.kubernetes.io/ssl-redirect" | string | `"true"` |  |
| nginx.ingress.annotations."kubernetes.io/ingress.class" | string | `"azure/application-gateway"` |  |
| nginx.ingress.enabled | bool | `false` |  |
| nginx.ingress.extraTls[0].hosts[0] | string | `"ddhub-dev.energyweb.org"` |  |
| nginx.ingress.extraTls[0].secretName | string | `"dsb-tls-secret"` |  |
| nginx.ingress.hostname | string | `"ddhub-dev.energyweb.org"` |  |
| nginx.ingress.path | string | `"/"` |  |
| nginx.ingress.pathType | string | `"Prefix"` |  |
| nginx.ingress.tls | bool | `false` |  |
| nginx.livenessProbe.enabled | bool | `false` |  |
| nginx.readinessProbe.enabled | bool | `false` |  |
| nginx.serverBlock | string | `"server {\n  listen 0.0.0.0:8080;\n  server_name  _;\n  location ~ ^/(backend-docs|backend-health) {\n      proxy_pass http://backend-server.namespace.svc.cluster.local;\n  }\n  location ~ ^/auth {\n      proxy_pass http://did-auth-proxy-helm.namespace.svc.cluster.local;\n  }\n  location ~ / {\n      auth_request /token_introspection;\n      proxy_pass http://backend-server.namespace.svc.cluster.local;\n  }\n  location = /token_introspection {\n        internal;\n        proxy_method      GET;\n        proxy_set_header  Authorization \"$http_authorization\";\n        proxy_set_header  Content-Length \"\";\n        proxy_pass        http://did-auth-proxy-helm.namespace.svc.cluster.local/auth/token-introspection;\n  }\n}"` |  |
| nginx.service.type | string | `"ClusterIP"` |  |
| nodeSelector | object | `{}` |  |
| opsValues.CACHE_SERVER_URL | string | `"https://identitycache-dev.energyweb.org/v1"` |  |
| opsValues.REDIS_HOST | string | `"did-auth-proxy-helm-redis-master.did.svc.cluster.local"` |  |
| opsValues.REDIS_PORT | int | `6379` |  |
| opsValues.RPC_URL | string | `"https://volta-rpc.energyweb.org/"` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| redis.auth.password | string | `"redis"` |  |
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
