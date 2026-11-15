---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Logs and observability

[🇬🇧 English](03-observability.md) · [🇨🇴 Español](03-observability.es.md) · [↩ Kubernetes](README.md)

**Platform:** Kubernetes / kubectl; examples pending lab validation.

## `kubectl logs -n automation deployment/awx-web --tail=100`

```bash
kubectl logs -n automation deployment/awx-web --tail=100
```

- **Purpose:** Read the last 100 container log lines for a deployment when the target resolves unambiguously.
- **Arguments:** `-n automation`: namespace; `deployment/awx-web`: target workload; `--tail=100`: last 100 lines.
- **Use case:** Investigate an AWX web service error without streaming unlimited logs.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_logs/

> Not lab-verified. Logs may contain sensitive data.

## `kubectl get events -n automation --sort-by=.metadata.creationTimestamp`

```bash
kubectl get events -n automation --sort-by=.metadata.creationTimestamp
```

- **Purpose:** List namespace events ordered by their creation timestamp.
- **Arguments:** `get events`: list Event objects; `-n`: namespace; `--sort-by`: sort client-side by JSONPath field.
- **Use case:** Correlate pod scheduling failures and image-pull errors.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_get/

> Not lab-verified. Logs may contain sensitive data.
