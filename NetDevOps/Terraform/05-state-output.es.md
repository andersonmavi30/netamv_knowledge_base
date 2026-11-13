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

## `terraform output -json`

```bash
terraform output -json
```

- **Sirve para:** Mostrar salidas del módulo raíz en formato JSON para automatización.
- **Parámetros:** `output`: lee salidas raíz; `-json`: JSON estructurado que puede revelar valores sensibles en texto plano.
- **Ejemplo de uso:** Usar identificadores no secretos autorizados dentro de un flujo CI/CD.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/output

> Pendiente de validación en laboratorio. No publiques salidas JSON con secretos.
