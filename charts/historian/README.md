# Historian Helm Chart

This chart deploys the Historian to a Kubernetes cluster.

> The implementation of the Helm chart is right now the bare minimum to get it to work.

## Usage in Teknoir platform
Use the HelmChart to deploy the Historian to a Device.

```yaml
---
apiVersion: helm.cattle.io/v1
kind: HelmChart
metadata:
  name: historian
  namespace: default
spec:
  repo: https://teknoir.github.io/historian-helm
  chart: historian
  targetNamespace: default
  valuesContent: |-
    # TBD
```

## Example values.yaml

```yaml
# TBD
```

## Adding the repository

```bash
helm repo add teknoir-historian https://teknoir.github.io/historian-helm/
```

## Installing the chart

```bash
helm install historian teknoir-historian/historian -f values.yaml
```