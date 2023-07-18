# gnomad-legacy-redirects

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 75636d6](https://img.shields.io/badge/AppVersion-75636d6-informational?style=flat-square)

A Helm chart for deploying the gnomad legacy-redirects service

**Homepage:** <https://gnomad.broadinstitute.org>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| broadinstitute/gnomad-browser |  | <https://gnomad.broadinstitute.org> |

## Source Code

* <https://github.com/broadinstitute/gnomad-helm>
* <https://github.com/broadinstitute/gnomad-redirect>

## Installation

1. `helm repo add gnomad broadinstitute.github.io/gnomad-helm`
2. `helm install --set 'ingress.managed_cert=true' --set 'gcp_global_ip=1.2.3.4' gnomad-legacy-redirects gnomad/gnomad-legacy-redirects`

## Customization

The deployment can be customized by overriding the defaults in values.yaml using any of the methods described in the [`helm install` docs](https://helm.sh/docs/helm/helm_install/)

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| fullnameOverride | string | `""` |  |
| gcp_global_ip | string | `"0.0.0.0"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"gcr.io/exac-gnomad/legacy-redirects"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.enabled | bool | `true` |  |
| ingress.host | string | `"exac.broadinstitute.org"` |  |
| ingress.managed_cert | bool | `false` |  |
| ingress.paths[0].path | string | `"/*"` |  |
| ingress.paths[0].pathType | string | `"ImplementationSpecific"` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources.limits.cpu | string | `"100m"` |  |
| resources.limits.memory | string | `"32Mi"` |  |
| resources.requests.cpu | string | `"10m"` |  |
| resources.requests.memory | string | `"32Mi"` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| tolerations | list | `[]` |  |
