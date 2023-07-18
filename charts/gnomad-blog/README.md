# gnomad-blog

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: bff889b8](https://img.shields.io/badge/AppVersion-bff889b8-informational?style=flat-square)

A Helm chart for deploying the gnomad-blog

**Homepage:** <https://gnomad.broadinstitute.org>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| broadinstitute/gnomad-browser |  | <https://gnomad.broadinstitute.org> |

## Source Code

* <https://github.com/broadinstitute/gnomad-helm>
* <https://github.com/broadinstitute/gnomad-blog>

## Requirements

This chart uses an ExternalSecret manifest to sync secrets from the GCP secret manager to our kubernetes cluster. You must define a GCP secret with a JSON document containing k/v pairs for the blog OAuth client and secret IDs, and then grant your GKE cluster's service account roles/secretmanager.secretAccessor permissions on that secret. The name of the GCP secret can then be passed into the chart with the `gcp_blog_oauth_secrets_name` variable.

Example GCP secret value:

```json
{"client-id": "abc123", "client-secret": "def345"}
```

## Installation

1. `helm repo add gnomad broadinstitute.github.io/gnomad-helm`
2. `helm install --set 'proxy_ips="1.2.3.4,0.0.0.0"' gnomad-blog gnomad/gnomad-blog`

## Customization

The deployment can be customized by overriding the defaults in values.yaml using any of the methods described in the [`helm install` docs](https://helm.sh/docs/helm/helm_install/)

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| fullnameOverride | string | `""` |  |
| gcp_blog_oauth_secrets_name | string | `"blog-oauth-secrets"` |  |
| images.authImage.tag | string | `""` |  |
| images.webImage.tag | string | `""` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| proxy_ips | string | `"127.0.0.1,0.0.0.0"` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| secrets_cluster_secretstore_name | string | `"gcpsm"` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
