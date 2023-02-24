# FullStack DevOps collection of helm charts

## Usage

[Helm](https://helm.sh) must be installed to use the charts. Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

    helm repo add fs-devops https://fullstack-devops.github.io/helm-charts/

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages. You can then run `helm search repo fsops` to see the charts.

To install a chart:

    helm install my-<chart-name> fs-devops/<chart-name>

To uninstall the chart:

    helm delete my-<chart-name>

## Charts

| Name                  | Description                     | Docs                                  |
| --------------------- | ------------------------------- | ------------------------------------- |
| excalidraw            | Chart for excalidraw            | [link](charts/excalidraw/)            |
| github-actions-runner | Chart for github-actions-runner | [link](charts/github-actions-runner/) |

## Dev

### helm-docs

```bash
go install github.com/norwoodj/helm-docs/cmd/helm-docs@latest
helm-docs -t templates/README.md.gotmpl
```

### Pre-commit hook

If you want to automatically generate `README.md` files with a pre-commit hook, make sure you
[install the pre-commit binary](https://pre-commit.com/#install), and add a [.pre-commit-config.yaml file](./.pre-commit-config.yaml)
to your project. Then run:

```bash
pre-commit install
pre-commit install-hooks
```

Future changes to your chart's `requirements.yaml`, `values.yaml`, `Chart.yaml`, or `README.md.gotmpl` files will cause an update to documentation when you commit.
