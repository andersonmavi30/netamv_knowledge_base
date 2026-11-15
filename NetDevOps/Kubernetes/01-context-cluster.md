---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Context and cluster

[🇬🇧 English](01-context-cluster.md) · [🇨🇴 Español](01-context-cluster.es.md) · [↩ Kubernetes](README.md)

**Platform:** Kubernetes / kubectl; examples pending lab validation.

## `kubectl version --client`

```bash
kubectl version --client
```

- **Purpose:** Display the installed kubectl client version without contacting the cluster.
- **Arguments:** `version`: version information; `--client`: client only, no API-server query.
- **Use case:** Verify the CLI before administering a K3s lab.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_version/

> Not lab-verified.

## `kubectl config current-context`

```bash
kubectl config current-context
```

- **Purpose:** Display the active kubeconfig context, which identifies the selected cluster/user configuration.
- **Arguments:** `config current-context`: read active context; no modifications.
- **Use case:** Avoid operating on production while intending to access a K3s lab.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_config/kubectl_config_current-context/

> Not lab-verified.

## `kubectl get nodes -o wide`

```bash
kubectl get nodes -o wide
```

- **Purpose:** List cluster nodes with readiness and additional node/network columns.
- **Arguments:** `get nodes`: list Node objects; `-o wide`: extra columns including internal IP when available.
- **Use case:** Check K3s node readiness before deploying AWX workloads.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Not lab-verified.
