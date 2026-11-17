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

## `terraform validate -json`

```bash
terraform validate -json
```

- **Sirve para:** Validar la configuración y emitir diagnósticos JSON para herramientas CI.
- **Parámetros:** `validate`: validación estática tras init; `-json`: diagnósticos legibles por máquinas, no prueba recursos remotos.
- **Ejemplo de uso:** Procesar errores de validación en un pipeline GitLab o Jenkins.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/validate

> Pendiente de validación en laboratorio.

## `terraform fmt -recursive`

```bash
terraform fmt -recursive
```

- **Sirve para:** Reformatear archivos de Terraform dentro del árbol de directorios al estilo oficial.
- **Parámetros:** `fmt`: modifica archivos; `-recursive`: incluye subdirectorios; revisar `git diff` después.
- **Ejemplo de uso:** Normalizar archivos IaC en una rama feature antes del merge request.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/fmt

> Pendiente de validación en laboratorio.
