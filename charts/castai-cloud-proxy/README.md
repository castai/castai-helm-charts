# castai-cloud-proxy

CAST AI cloud-proxy chart

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| additionalEnv | object | `{"LOG_LEVEL":"4"}` | Used to set additional environment variables for the cloud-proxy container. |
| affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.labelSelector.matchExpressions[0].key | string | `"app.kubernetes.io/name"` |  |
| affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.labelSelector.matchExpressions[0].operator | string | `"In"` |  |
| affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.labelSelector.matchExpressions[0].values[0] | string | `"castai-cloud-proxy"` |  |
| affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].podAffinityTerm.topologyKey | string | `"kubernetes.io/hostname"` |  |
| affinity.podAntiAffinity.preferredDuringSchedulingIgnoredDuringExecution[0].weight | int | `100` |  |
| castai | object | `{"apiKey":"","apiKeySecretRef":"","clusterID":"","grpcURL":"api-grpc.cast.ai:443","useCompression":true}` | CAST AI specific settings |
| castai.apiKey | string | `""` | The CAST AI API key. Either this or apiKeySecretRef must be provided. |
| castai.apiKeySecretRef | string | `""` | Kubernetes Secret reference for the CAST AI API key. Either this or apiKey must be provided. |
| castai.clusterID | string | `""` | The CAST AI cluster ID. |
| castai.grpcURL | string | `"api-grpc.cast.ai:443"` | The CAST AI gRPC URL. |
| castai.useCompression | bool | `true` | Use compression for gRPC communication. |
| commonAnnotations | object | `{}` |  |
| fullnameOverride | string | `""` |  |
| gke.auth | object | `{"jsonCredentials":""}` | Optional: by default metadata server is used. Override this options to choose another authentication method. (https://cloud.google.com/docs/authentication/application-default-credentials). |
| gke.auth.jsonCredentials | string | `""` | JSON credentials to use when authenticating against GCP. You can generate the JSON key using this documentation: https://cloud.google.com/iam/docs/keys-create-delete#creating |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"us-docker.pkg.dev/castai-hub/library/cloud-proxy"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| livenessProbe.failureThreshold | int | `3` |  |
| livenessProbe.httpGet.path | string | `"/livez"` |  |
| livenessProbe.httpGet.port | int | `9091` |  |
| livenessProbe.periodSeconds | int | `10` |  |
| livenessProbe.successThreshold | int | `1` |  |
| livenessProbe.timeoutSeconds | int | `1` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| priorityClass.enabled | bool | `true` |  |
| priorityClass.name | string | `"system-cluster-critical"` |  |
| readinessProbe.failureThreshold | int | `3` |  |
| readinessProbe.httpGet.path | string | `"/readyz"` |  |
| readinessProbe.httpGet.port | int | `9091` |  |
| readinessProbe.periodSeconds | int | `10` |  |
| readinessProbe.successThreshold | int | `1` |  |
| readinessProbe.timeoutSeconds | int | `1` |  |
| replicaCount | int | `2` |  |
| resources.limits.cpu | int | `1` |  |
| resources.limits.memory | string | `"512Mi"` |  |
| resources.requests.cpu | string | `"100m"` |  |
| resources.requests.memory | string | `"128Mi"` |  |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| securityContext.readOnlyRootFilesystem | bool | `true` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `1000` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.automount | bool | `true` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |
