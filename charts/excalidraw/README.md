# excalidraw

![Version: 0.2.9](https://img.shields.io/badge/Version-0.2.9-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.7](https://img.shields.io/badge/AppVersion-0.0.7-informational?style=flat-square)

A Helm chart for Kubernetes

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/fullstack-devops/helm-charts/issues/new/choose)**

## Source Code

* <https://github.com/fullstack-devops/excalidraw>
* <https://github.com/fullstack-devops/excalidraw/pkgs/container/excalidraw>
* <https://quay.io/repository/fullstack-devops/excalidraw>

## Requirements

- Kubernetes: `>=1.19.0`
- Helm 3.2.0+
- PV provisioner support in the underlying infrastructure

## Dependencies

| Repository | Name | Version |
|------------|------|---------|

## TL;DR

```console
helm repo add fs-devops https://fullstack-devops.github.io/helm-charts/
helm repo update
helm install excalidraw fs-devops/excalidraw
```

## Installing the Chart

To install the chart with the release name `excalidraw`

```console
helm install excalidraw fs-devops/excalidraw
```

## Uninstalling the Chart

To uninstall the `excalidraw` deployment

```console
helm uninstall excalidraw
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install excalidraw \
  --set env.TZ="America/New York" \
    fs-devops/excalidraw
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install excalidraw fs-devops/excalidraw -f values.yaml
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"quay.io/fullstack-devops/excalidraw"` | image repository |
| image.tag | string | `""` | image tag (default is the chart appVersion) |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | dict | `{}` | Custom Ingress annotations |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` | Set to true to generate Ingress resource |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | string | `"150m"` |  |
| resources.limits.memory | string | `"256Mi"` |  |
| resources.requests.cpu | string | `"20m"` |  |
| resources.requests.memory | string | `"128Mi"` |  |
| securityContext.readOnlyRootFilesystem | bool | `false` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `101` |  |
| service.port | int | `80` | Specify service port |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `false` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |

