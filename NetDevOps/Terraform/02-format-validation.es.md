---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Formato y validación

[🇬🇧 English](02-format-validation.md) · [🇨🇴 Español](02-format-validation.es.md) · [↩ Terraform](README.es.md)

**Plataforma:** Terraform CLI 1.x; ejemplos pendientes de prueba en laboratorio.

## `terraform fmt -check -recursive -diff`

```bash
terraform fmt -check -recursive -diff
```

- **Sirve para:** Comprobar formato de archivos Terraform del directorio actual y subdirectorios sin reescribirlos.
- **Parámetros:** `-check`: código de salida distinto de cero si hay diferencias; `-recursive`: subdirectorios; `-diff`: mostrar cambios.
- **Ejemplo de uso:** Validar estilo del código en un pull request antes del merge.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/fmt

> Pendiente de validación en laboratorio.

## `terraform validate -no-color`

```bash
terraform validate -no-color
```

- **Sirve para:** Validar sintaxis y consistencia interna tras inicializar el directorio.
- **Parámetros:** `validate`: valida configuración, no recursos remotos; `-no-color`: salida de texto para logs CI.
- **Ejemplo de uso:** Detectar argumentos o referencias de módulos inválidos antes de planificar.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/validate

> Pendiente de validación en laboratorio.
