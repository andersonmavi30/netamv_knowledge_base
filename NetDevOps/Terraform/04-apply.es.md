---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Aplicación y ejecución

[🇬🇧 English](04-apply.md) · [🇨🇴 Español](04-apply.es.md) · [↩ Terraform](README.es.md)

**Plataforma:** Terraform CLI 1.x; ejemplos pendientes de prueba en laboratorio.

## `terraform apply -input=false tfplan`

```bash
terraform apply -input=false tfplan
```

- **Sirve para:** Aplicar un plan previamente guardado, que puede crear, modificar o destruir recursos.
- **Parámetros:** `-input=false`: desactiva preguntas interactivas; `tfplan`: plan revisado; ejecuta cambios reales.
- **Ejemplo de uso:** Ejecutar cambio aprobado en laboratorio tras revisar plan y workspace.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/apply

> Pendiente de validación en laboratorio. Precaución: ejecuta cambios reales, confirmar aprobación.
