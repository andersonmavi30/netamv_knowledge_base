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
