---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Planificación e inspección

[🇬🇧 English](03-planning.md) · [🇨🇴 Español](03-planning.es.md) · [↩ Terraform](README.es.md)

**Plataforma:** Terraform CLI 1.x; ejemplos pendientes de prueba en laboratorio.

## `terraform plan -var-file=lab.tfvars -out=tfplan`

```bash
terraform plan -var-file=lab.tfvars -out=tfplan
```

- **Sirve para:** Crear y guardar un plan usando variables de laboratorio sin aplicar cambios de recursos.
- **Parámetros:** `-var-file=lab.tfvars`: carga variables; `-out=tfplan`: guarda plan binario potencialmente sensible.
- **Ejemplo de uso:** Revisar cambios de infraestructura antes de aprobarlos.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Pendiente de validación en laboratorio. No publicar planes o archivos de variables con secretos.

## `terraform show -no-color tfplan`

```bash
terraform show -no-color tfplan
```

- **Sirve para:** Leer el plan guardado con salida legible sin códigos de color.
- **Parámetros:** `-no-color`: elimina colores ANSI; `tfplan`: plan guardado con posibles secretos.
- **Ejemplo de uso:** Inspeccionar el plan guardado antes de desplegar.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/show

> Pendiente de validación en laboratorio. 
