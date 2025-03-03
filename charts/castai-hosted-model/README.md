# castai-hosted-model

CAST AI hosted model deployment chart.

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| file://child-charts/vllm | vllm | 0.0.4 |
| https://otwld.github.io/ollama-helm/ | ollama | 1.4.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| ollama.enabled | bool | `true` | Specifies if Ollama model should be deployed |
| placementJob.enabled | bool | `false` | Specifies if a node placement job should be deployed |
| placementJob.image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| placementJob.image.repository | string | `"busybox"` | The image to use for the job |
| placementJob.image.tag | string | `"1.37.0"` | The image tag |
| placementJob.requiredGPUTotalMemoryMiB | string | `nil` | Total GPU memory MiB (GPU count * GPU memory MiB) of the node that should be provisioned for this job |
| placementJob.resources | object | `{}` | Resources for the job |
| vllm.enabled | bool | `false` | Specifies if vLLM model should be deployed |