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

## `terraform show -no-color tfplan`

```bash
terraform show -no-color tfplan
```

- **Purpose:** Read a saved Terraform execution plan using plain terminal output.
- **Arguments:** `-no-color`: omit ANSI colors; `tfplan`: path to saved plan containing potentially sensitive data.
- **Use case:** Inspect the exact saved plan before an approved deployment.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/show

> Not lab-verified.

## `terraform providers`

```bash
terraform providers
```

- **Purpose:** List provider requirements from the current Terraform configuration and state.
- **Arguments:** `providers`: list required providers; no flags; displays dependency and provider information.
- **Use case:** Check which network or cloud providers the module needs before init.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/providers

> Not lab-verified. 
