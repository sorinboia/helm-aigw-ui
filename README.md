# AI Gateway Helm Chart

This chart deploys the AI Gateway components including:
- MinIO storage
- AI Gateway UI
- Service Account with cluster-admin privileges

## Configuration

The following table lists the configurable parameters:

| Parameter | Description | Default |
|-----------|-------------|---------|
| `namespace` | Kubernetes namespace | `aigw` |
| `serviceAccount.name` | Service account name | `full-access-sa` |
| `minio.image` | MinIO container image | `quay.io/minio/minio:latest` |
| `minio.accessKey` | MinIO access key | `minioadmin` |
| `minio.secretKey` | MinIO secret key | `minioadmin` |
| `minio.bucketName` | Default bucket name | `aigw` |
| `minio.apiPort` | MinIO API port | `9000` |
| `minio.consolePort` | MinIO Console port | `3090` |
| `aigwUi.image` | AI Gateway UI image | `sorinboiaf5/aigw-ui:latest` |
| `aigwUi.port` | AI Gateway UI port | `3080` |

## Installation

1. Install the chart:
```bash
helm install aigw ./aigw-chart -f custom-values.yaml
```

2. To upgrade:
```bash
helm upgrade aigw ./aigw-chart -f custom-values.yaml
```
