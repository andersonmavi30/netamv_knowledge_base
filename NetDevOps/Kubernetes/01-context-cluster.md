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
