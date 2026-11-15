---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Workloads and resources

[🇬🇧 English](02-workloads.md) · [🇨🇴 Español](02-workloads.es.md) · [↩ Kubernetes](README.md)

**Platform:** Kubernetes / kubectl; examples pending lab validation.

## `kubectl get pods -n automation -o wide`

```bash
kubectl get pods -n automation -o wide
```

- **Purpose:** Inspect pods in the automation namespace, including node assignment and pod IP.
- **Arguments:** `get pods`: list pods; `-n automation`: select namespace; `-o wide`: show extra columns.
- **Use case:** Locate the node hosting an AWX pod that is restarting.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Not lab-verified.
