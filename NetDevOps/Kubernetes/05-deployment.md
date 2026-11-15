---
tags: [kubernetes, kubectl, cli, netdevops]
validation: not-lab-verified
---

# Deployments and rollout

[🇬🇧 English](05-deployment.md) · [🇨🇴 Español](05-deployment.es.md) · [↩ Kubernetes](README.md)

**Platform:** Kubernetes / kubectl; examples pending lab validation.

## `kubectl rollout status deployment/awx-web -n automation --timeout=120s`

```bash
kubectl rollout status deployment/awx-web -n automation --timeout=120s
```

- **Purpose:** Wait for a Deployment rollout to complete and report whether it succeeds within two minutes.
- **Arguments:** `rollout status`: inspect rollout progress; `deployment/awx-web`: target; `-n`: namespace; `--timeout=120s`: maximum wait.
- **Use case:** Validate AWX web rollout after an authorized deployment without changing its configuration.
- **Official reference:** https://kubernetes.io/docs/reference/kubectl/generated/kubectl_rollout/kubectl_rollout_status/

> Not lab-verified.
