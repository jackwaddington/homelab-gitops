# homelab-gitops

GitOps repository for my [k3s cluster](https://github.com/jackwaddington/k3s), managed by [Argo CD](https://argo-cd.readthedocs.io/).

## Cluster

- **3 nodes:** 1 master (`k3s-master`) + 2 workers (`k3s-worker1`, `k3s-worker2`)
- **Distribution:** k3s v1.31.6
- **GitOps:** Argo CD watches this repo and auto-deploys changes to the cluster

## Applications

| App | Namespace | Port | Source |
|---|---|---|---|
| [homepage](apps/homepage/) | default | 30080 | This repo |
| [monitoring](https://github.com/jackwaddington/jWorld-observability) | monitoring | 30300 (Grafana) | [jWorld-observability](https://github.com/jackwaddington/jWorld-observability) |

## Access

| Service | URL |
|---|---|
| Argo CD | `https://<node-ip>:30443` |
| Grafana | `http://<node-ip>:30300` |
| Homepage | `http://<node-ip>:30080` |

## Repo Structure

```
apps/
  homepage/
    configmap.yaml
    deployment.yaml
    serviceaccount.yaml
    service.yaml
```
