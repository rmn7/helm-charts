# kubecost-reports-exporter

![Version: 1.1.0](https://img.shields.io/badge/Version-1.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.5](https://img.shields.io/badge/AppVersion-1.0.5-informational?style=flat-square)

Helm chart for exporting kubernetes cost reports to S3

**Homepage:** <https://www.kubecost.com>

## How to install this chart

Add Delivery Hero public chart repo:

```console
helm repo add deliveryhero https://charts.deliveryhero.io/
```

A simple install with default values:

```console
helm install deliveryhero/kubecost-reports-exporter
```

To install the chart with the release name `my-release`:

```console
helm install my-release deliveryhero/kubecost-reports-exporter
```

To install with some set values:

```console
helm install my-release deliveryhero/kubecost-reports-exporter --set values_key1=value1 --set values_key2=value2
```

To install with custom values file:

```console
helm install my-release deliveryhero/kubecost-reports-exporter -f values.yaml
```

## Source Code

* <https://www.kubecost.com>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| concurrencyPolicy | string | `"Forbid"` |  |
| env | object | `{}` | Extra environment variables |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"thomasnyambati/kubecost-reports-exporter"` |  |
| imagePullSecrets | list | `[]` |  |
| kubecost.aggregatedCostUrl | string | `"/model/aggregatedCostModel?window=1d&aggregation=namespace"` | Url for aggregated cost report |
| kubecost.bucketName | string | `"kubecost-reports-exporter"` | S3 Bucket name for reports export |
| kubecost.clusterName | string | `"change_me"` | Name of the cluster |
| kubecost.clusters[0].endpoint | string | `"http://kubecost-cost-analyzer:9090"` |  |
| kubecost.clusters[0].name | string | `"default"` |  |
| kubecost.logLevel | string | `"info"` | exporter log level. |
| kubecost.nonAggregatedCostUrl | string | `"/model/costDataModel?timeWindow=1d&offset=1d"` | Url for non-aggregated cost report |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| resources | object | `{}` |  |
| restartPolicy | string | `"OnFailure"` |  |
| schedule | string | `"0 * * * *"` |  |
| securityContext | object | `{}` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `false` |  |
| serviceAccount.name | string | `""` |  |
| successfulJobsHistoryLimit | int | `1` |  |
| tolerations | list | `[]` |  |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| nyambati | thomas.nyambati@deliveryhero.com |  |
