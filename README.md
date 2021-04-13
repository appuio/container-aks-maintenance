# container-aks-maintenance

[![Build Status](https://img.shields.io/github/workflow/status/appuio/container-aks-maintenance/Main)](https://github.com/appuio/container-aks-maintenance/actions/workflows/main.yaml)
[![License](https://img.shields.io/github/license/appuio/container-aks-maintenance.svg)](https://github.com/appuio/container-aks-maintenance/blob/master/LICENSE)


`aks-maintenance` in a container image that can be used to do AKS Node Maintenance based on [AKS Node Maintenance](https://kb.vshn.ch/rancher/how-tos/aks_node_maintenance.html)

The built images are available from

* [Docker Hub][hub]
* [Quay.io][quay]


## Contents

- `az` CLI
- `updateNodes.sh`

> [APPUiO](https://appuio.ch) -
> GitHub [@appuio](https://github.com/appuio) -
> Twitter [@appuio](https://twitter.com/appuio)

## Usage

### Nodepool image upgrade

```bash
docker run -it docker.io/appuio/aks-maintenance: updateNodes.sh <resource-group> <cluster-name> <nodepool-name> [apply]
```

Sample Output:


```
docker run -it docker.io/appuio/aks-maintenance updateNodes.sh xxxx xxxx workers
To sign in, use a web browser to open the page https://microsoft.com/devicelogin and enter the code xxxxxxx to authenticate.
The following tenants don't contain accessible subscriptions. Use 'az login --allow-no-subscriptions' to have tenant level access.
xxxx
[
  {
    "cloudName": "AzureCloud",
    "homeTenantId": "xxxx",
    "id": "xxxx",
    "isDefault": true,
    "managedByTenants": [],
    "name": "xxxx",
    "state": "Enabled",
    "tenantId": "xxxx",
    "user": {
      "name": "xxxx",
      "type": "user"
    }
  }
]
Checking nodepool image upgrade
  Resource group: 'xxxx'
  Cluster name: 'xxxx'
  Nodepool: 'workers'

Latest nodepool image version: 'AKSUbuntu-1804-2021.03.29'
Curent nodepool image version: 'AKSUbuntu-1804-2021.02.17'

-> Nodepool image upgrade required
-> please add apply to your command to upgrade
```


## Build the image

```console
make docker-build
```
