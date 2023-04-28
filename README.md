# gnomAD Project Helm Charts

This repository contains the [Helm](https://helm.sh) Charts for deploying the gnomAD browser and its surrounding components.


## Inventory

- [gnomAD Browser](./charts/gnomad-browser)
- [elasticsearch](./charts/gnomad-elasticsearch)
- [ingress](./charts/gnomad-ingress)
	- A chart for managing ingress separately from the browser deployment. This is useful for cases when you want to deploy a single ingress with many services behind it.
