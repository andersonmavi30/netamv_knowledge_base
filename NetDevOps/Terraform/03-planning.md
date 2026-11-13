---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Planning and inspection

[🇬🇧 English](03-planning.md) · [🇨🇴 Español](03-planning.es.md) · [↩ Terraform](README.md)

**Platform:** Terraform CLI 1.x; examples pending lab validation.

## `terraform plan -var-file=lab.tfvars -out=tfplan`

```bash
terraform plan -var-file=lab.tfvars -out=tfplan
```

- **Purpose:** Create and save an execution plan using lab variables without applying resource changes.
- **Arguments:** `-var-file=lab.tfvars`: load values from file; `-out=tfplan`: save binary plan, potentially sensitive.
- **Use case:** Review proposed infrastructure changes before an approval gate.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Not lab-verified. Do not publish plans or variable files containing secrets.
