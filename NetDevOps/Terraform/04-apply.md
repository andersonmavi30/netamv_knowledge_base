---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Apply and execution

[🇬🇧 English](04-apply.md) · [🇨🇴 Español](04-apply.es.md) · [↩ Terraform](README.md)

**Platform:** Terraform CLI 1.x; examples pending lab validation.

## `terraform apply -input=false tfplan`

```bash
terraform apply -input=false tfplan
```

- **Purpose:** Apply a previously generated saved plan, potentially creating, changing or destroying managed resources.
- **Arguments:** `-input=false`: disable interactive input; `tfplan`: reviewed saved plan; execution changes real infrastructure.
- **Use case:** Execute an approved lab change after checking plan freshness and workspace.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/apply

> Not lab-verified. Caution: executes real changes; require approval.
