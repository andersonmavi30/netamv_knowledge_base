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

## `terraform plan -detailed-exitcode -no-color`

```bash
terraform plan -detailed-exitcode -no-color
```

- **Purpose:** Generate a plan with exit codes to distinguish no changes, planned changes, and errors.
- **Arguments:** `-detailed-exitcode`: 0 no changes, 2 changes, 1 error; `-no-color`: remove ANSI codes.
- **Use case:** Use the exit code as a CI gate before proposing infrastructure deployment.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Not lab-verified.

## `terraform plan -refresh-only`

```bash
terraform plan -refresh-only
```

- **Purpose:** Propose updates to state and outputs to reflect remote changes without planning infrastructure modifications.
- **Arguments:** `-refresh-only`: refresh state/output values without suggesting remote object changes; planning may contact APIs.
- **Use case:** Detect drift between tracked state and live network resources.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Not lab-verified.

## `terraform plan -destroy`

```bash
terraform plan -destroy
```

- **Purpose:** Preview which managed resources would be destroyed, without executing the destruction.
- **Arguments:** `plan`: preview; `-destroy`: plan removal of all managed objects in this configuration; no apply.
- **Use case:** Assess the impact of tearing down a disposable lab environment.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Not lab-verified.

## `terraform graph -type=plan`

```bash
terraform graph -type=plan
```

- **Purpose:** Emit the planned dependency graph in DOT format for analysis or Graphviz rendering.
- **Arguments:** `graph`: produce DOT output; `-type=plan`: represent planning operations; no infrastructure changes.
- **Use case:** Inspect module/resource dependencies before network infrastructure changes.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/graph

> Not lab-verified.
