---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# State and outputs

[🇬🇧 English](05-state-output.md) · [🇨🇴 Español](05-state-output.es.md) · [↩ Terraform](README.md)

**Platform:** Terraform CLI 1.x; examples pending lab validation.

## `terraform state list`

```bash
terraform state list
```

- **Purpose:** List Terraform resource addresses currently tracked in state.
- **Arguments:** `state list`: read resource addresses from current state; requires backend access and may expose resource names.
- **Use case:** Confirm managed resources before an import or state maintenance task.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/state/list

> Not lab-verified. 
