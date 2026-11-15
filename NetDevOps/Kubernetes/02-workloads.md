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

## `kubectl describe pod awx-web -n automation`

```bash
kubectl describe pod awx-web -n automation
```

- **Purpose:** Show detailed pod state, conditions and scheduling events.
- **Arguments:** `describe pod awx-web`: inspect named pod; `-n automation`: select namespace.
- **Use case:** Diagnose why an AWX web pod is Pending or not Ready; replace example names.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_describe/

> Not lab-verified. Logs may contain sensitive data.
