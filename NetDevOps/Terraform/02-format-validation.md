---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Formatting and validation

[🇬🇧 English](02-format-validation.md) · [🇨🇴 Español](02-format-validation.es.md) · [↩ Terraform](README.md)

**Platform:** Terraform CLI 1.x; examples pending lab validation.

## `terraform fmt -check -recursive -diff`

```bash
terraform fmt -check -recursive -diff
```

- **Purpose:** Check Terraform files in current directory and nested directories for canonical formatting without rewriting them.
- **Arguments:** `-check`: nonzero exit for needed formatting; `-recursive`: subdirectories; `-diff`: display formatting differences.
- **Use case:** Validate code style in a pull request before merge.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/fmt

> Not lab-verified.

## `terraform validate -no-color`

```bash
terraform validate -no-color
```

- **Purpose:** Validate configuration syntax and internal consistency after initialization.
- **Arguments:** `validate`: checks configuration, not live cloud/API resources; `-no-color`: plain output for CI logs.
- **Use case:** Catch invalid arguments or module references before planning.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/validate

> Not lab-verified.
