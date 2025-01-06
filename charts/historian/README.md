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
    historianApi:
      enabled: false
    
    metricsExporter:
      enabled: false
    
    image:
      repository: mongo
      tag: 7.0.15
    
    annotations:
      teknoir.org/managed-by: devstudio
    resources:
      limits:
        cpu: 2000m
        memory: 2048Mi
      requests:
        cpu: 200m
        memory: 128Mi
    nodePort:
      enabled: false
      nodePort: 31017
```

## Example values.yaml

```yaml
nodePort:
  enabled: true
```

## Adding the repository

```bash
helm repo add teknoir-historian https://teknoir.github.io/historian-helm/
```

## Installing the chart

```bash
helm install historian teknoir-historian/historian -f values.yaml
```