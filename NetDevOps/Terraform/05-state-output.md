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

## `terraform output -json`

```bash
terraform output -json
```

- **Purpose:** Render root module output values in machine-readable JSON.
- **Arguments:** `output`: read root outputs; `-json`: structured JSON, which can expose sensitive values in plaintext.
- **Use case:** Pass approved non-secret resource identifiers into a CI/CD workflow.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/output

> Not lab-verified. Never publish JSON outputs containing secrets.

## `terraform state show 'module.network.null_resource.lab'`

```bash
terraform state show 'module.network.null_resource.lab'
```

- **Purpose:** Inspect one resource instance recorded in Terraform state.
- **Arguments:** `state show`: read resource details; quoted address: illustrative resource address to replace with one from `terraform state list`.
- **Use case:** Inspect the recorded attributes of a disposable network lab resource; output may contain sensitive information.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/state/show

> Not lab-verified.

## `terraform output -raw gateway_ip`

```bash
terraform output -raw gateway_ip
```

- **Purpose:** Print a single root-module output as an unquoted string for scripting.
- **Arguments:** `output`: read output; `-raw`: plain scalar value; `gateway_ip`: sample output name; sensitive values may be exposed.
- **Use case:** Read an approved gateway address in a network automation script.
- **Official reference:** https://developer.hashicorp.com/terraform/cli/commands/output

> Not lab-verified.
