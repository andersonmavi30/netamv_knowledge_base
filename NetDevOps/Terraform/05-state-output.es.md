---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Estado y salidas

[🇬🇧 English](05-state-output.md) · [🇨🇴 Español](05-state-output.es.md) · [↩ Terraform](README.es.md)

**Plataforma:** Terraform CLI 1.x; ejemplos pendientes de prueba en laboratorio.

## `terraform state list`

```bash
terraform state list
```

- **Sirve para:** Listar las direcciones de recursos registradas en el estado Terraform.
- **Parámetros:** `state list`: consulta direcciones de recursos; requiere backend y puede revelar nombres.
- **Ejemplo de uso:** Comprobar recursos administrados antes de importar o mantener el estado.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/state/list

> Pendiente de validación en laboratorio. 
