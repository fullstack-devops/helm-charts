# github-actions-runner

![Version: 0.7.0](https://img.shields.io/badge/Version-0.7.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.13.0](https://img.shields.io/badge/AppVersion-0.13.0-informational?style=flat-square)

A Helm chart for Kubernetes

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/fullstack-devops/helm-charts/issues/new/choose)**

## Source Code

* <https://github.com/fullstack-devops/github-actions-runner>
* <https://quay.io/repository/fullstack-devops/github-actions-runner>

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
helm install github-actions-runner fs-devops/github-actions-runner
```

## Installing the Chart

To install the chart with the release name `github-actions-runner`

```console
helm install github-actions-runner fs-devops/github-actions-runner
```

## Uninstalling the Chart

To uninstall the `github-actions-runner` deployment

```console
helm uninstall github-actions-runner
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install github-actions-runner \
  --set env.TZ="America/New York" \
    fs-devops/github-actions-runner
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install github-actions-runner fs-devops/github-actions-runner -f values.yaml
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `20` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/fullstack-devops/github-actions-runner"` | image repository |
| image.tag | string | `""` | image tag (default is the chart appVersion) |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| runner.additionalFiles.maven.settingsXml | tpl/dict |  | example settings.xml, will be placed in global .m2 folder |
| runner.customCerts.configMapRef | string | `""` |  |
| runner.env | list | `[]` | inject the runner custom env variables |
| runner.flavor.name | string | `"fullstacked"` |  |
| runner.flavor.override | bool | `false` | if override: true -> the runner.flavor will be ignored and image.repository and image.tag will be leading |
| runner.github.accessToken | string | `""` |  |
| runner.github.enterpriseApiUrl | string | `""` |  |
| runner.github.enterpriseUrl | string | `""` |  |
| runner.github.organisation | string | `"fullstack-devpos"` |  |
| runner.github.repository | string | `""` |  |
| runner.group | string | `""` |  |
| runner.kaniko.enabled | bool | `false` |  |
| runner.kaniko.image.repository | string | `""` |  |
| runner.kaniko.mountedSecret | string | `""` |  |
| runner.labels | string | `""` |  |
| runner.proxy.enabled | bool | `false` |  |
| runner.proxy.ntmlCreds | string | `""` |  |
| runner.proxy.pacUrl | string | `""` |  |
| securityContext.readOnlyRootFilesystem | bool | `false` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `1000` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `false` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |

