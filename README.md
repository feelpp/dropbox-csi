# Kubernetes CSI for Dropbox ![Dropbox-CSI](https://github.com/feelpp/dropbox-csi/workflows/Dropbox-CSI/badge.svg?branch=master)
## Overview
Kubernetes Dropbox-CSI plugin is developed to manage dropbox on kubernetes.

## How to use
### Create Secret
To connect your dropbox as persistent volume, you need to generate your dropbox access token.

1. visit link: https://www.dropbox.com/developers/apps
2. Create an app with `Full Dropbox` access type
3. Generate Access Token
4. Run command: `kubectl create secret generic dropbox-csi --from-literal=token={YOUR_TOKEN_HERE}`

### Deploy Dropbox-CSI Plugin
Deploy Dropbox-CSI plugin using Kubectl command.

```shell
kubectl create -f ./deploy/k8s-1.17/rbac.yaml 
kubectl create -f ./deploy/k8s-1.17/csi-dropbox-plugin.yaml 
kubectl create -f ./deploy/k8s-1.17/csi-dropbox-attacher.yaml
```

For now, you can make persistent volume with `dropbox.csi.k8s.io` driver. 

```shell
kubectl create -f deploy/pod.yaml
```

## Troubleshooting
Please submit an issue at [Issues](https://github.com/feelpp/dropbox-csi/issues).
You can use both english and korean. If you have other questions please contact: Woohyung Han (feelpp@gmail.com)
