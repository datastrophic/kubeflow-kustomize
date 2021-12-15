# Minimalistic Kubeflow Kustomize

This repo contains kustomizations for a demo installation of the Kubeflow based on
[kubeflow/manifests](https://github.com/kubeflow/manifests) repository.

The kustomizations in this repo modify base manifests to make them work with custom
Istio `Gateway` and OAuth2 Proxy headers.

The base installation includes the following:
- Kubeflow namespace and Roles
- Central Dashboard
- Notebook Spawner and Controller
- Profiles Controller and Auth Manager
- `PodDefaults` Webhook

Pre-requisites:
* A dedicated Istio Gateway installed at `ingress/ingress-gateway`

To generate manifests, run:
```
kubectl kustomize kubeflow
```

To install the distribution, run:
```
kubectl apply -k kubeflow
```
