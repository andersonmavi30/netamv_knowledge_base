---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Services and networking

[🇬🇧 English](04-networking.md) · [🇨🇴 Español](04-networking.es.md) · [↩ Kubernetes](README.md)

**Platform:** Kubernetes / kubectl; examples pending lab validation.

## `kubectl get svc -n automation -o wide`

```bash
kubectl get svc -n automation -o wide
```

- **Purpose:** List Kubernetes Services, their types, cluster IPs and exposed ports in the namespace.
- **Arguments:** `get svc`: list Services; `-n automation`: target namespace; `-o wide`: extra columns.
- **Use case:** Check how AWX web is exposed inside a K3s cluster.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Not lab-verified.
