# gnomAD Project Helm Charts

This repository contains the [Helm](https://helm.sh) Charts for deploying the gnomAD browser and its surrounding components.


## Inventory

- [gnomAD Browser and API](./charts/gnomad-browser)
- [gnomAD Blog](./charts/gnomad-blog)
- [Exome Results Browsers](./charts/exome-results)
- [gnomAD Reads service](./charts/gnomad-reads)
- [elasticsearch](./charts/gnomad-elasticsearch)
- [ingress](./charts/gnomad-ingress)
	- A chart for managing ingress separately from the browser deployment. This is useful for cases when you want to deploy a single ingress with many services behind it.
- [gnomAD Legacy Redirects service](./charts/legacy-redirects)


## Development

### Generating Documentation

After updating any helm chart values or updating the [README Template](./README.md.gotmpl) for a chart, you should regenerate the documentation using [helm-docs](https://github.com/norwoodj/helm-docs)

```bash
cd charts/chart-name  # the directory with Chart.yaml in it
helm-docs
```

### Testing

For charts that have tests, you need to have the [chart-testing](https://github.com/helm/chart-testing) and [KinD](https://github.com/kubernetes-sigs/kind) tools installed to run them locally.

```bash
# create a kubernetes-in-docker cluster, and make sure it is your current kubectl context
kind create cluster
# For private GCR registries, authenticate using an access token, using the kind-gcr.sh script: https://kind.sigs.k8s.io/docs/user/private-registries/#use-an-access-token
./kind-gcr.sh
# run ct from the root of the git repo to test any helm charts that have changed in your current branch, relevant to main
ct lint-and-install --target-branch main
```
