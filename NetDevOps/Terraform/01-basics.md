---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Basics and initialization

[🇬🇧 English](01-basics.md) · [🇨🇴 Español](01-basics.es.md) · [↩ Terraform](README.md)

**Platform:** Terraform CLI 1.x; examples pending lab validation.

## `terraform version`

```bash
terraform version
```

- **Purpose:** Display installed Terraform version and available provider version information.
- **Arguments:** `version`: read-only subcommand; no flags or infrastructure changes.
- **Use case:** Confirm CLI version before initializing an IaC project.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/version

> Not lab-verified.

## `terraform init -backend=false`

```bash
terraform init -backend=false
```

- **Purpose:** Initialize provider plugins and modules without initializing the configured backend.
- **Arguments:** `init`: prepare working directory; `-backend=false`: skip backend initialization (no remote state connection).
- **Use case:** Prepare a reusable module for validation in CI without accessing remote state.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/init

> Not lab-verified.
