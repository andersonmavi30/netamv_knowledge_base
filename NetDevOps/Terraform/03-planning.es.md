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

## `terraform providers`

```bash
terraform providers
```

- **Sirve para:** Listar requisitos de proveedores de la configuración y del estado actual.
- **Parámetros:** `providers`: lista proveedores requeridos, sin flags; muestra dependencias.
- **Ejemplo de uso:** Revisar proveedores de red o nube requeridos por el módulo antes de init.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/providers

> Pendiente de validación en laboratorio.

## `terraform plan -detailed-exitcode -no-color`

```bash
terraform plan -detailed-exitcode -no-color
```

- **Sirve para:** Generar un plan con códigos de salida que distinguen sin cambios, cambios previstos y errores.
- **Parámetros:** `-detailed-exitcode`: 0 sin cambios, 2 cambios, 1 error; `-no-color`: elimina códigos ANSI.
- **Ejemplo de uso:** Utilizar el código de salida para evaluar un pipeline CI antes del despliegue.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Pendiente de validación en laboratorio.

## `terraform plan -refresh-only`

```bash
terraform plan -refresh-only
```

- **Sirve para:** Proponer actualizaciones del estado y salidas según cambios remotos, sin planear modificaciones de infraestructura.
- **Parámetros:** `-refresh-only`: actualiza datos del estado y salidas sin proponer cambios remotos; puede consultar APIs.
- **Ejemplo de uso:** Detectar diferencias entre estado Terraform y recursos reales.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Pendiente de validación en laboratorio.

## `terraform plan -destroy`

```bash
terraform plan -destroy
```

- **Sirve para:** Previsualizar qué recursos administrados serían destruidos, sin ejecutar la eliminación.
- **Parámetros:** `plan`: previsualiza; `-destroy`: planifica eliminar todos los recursos administrados; no ejecuta.
- **Ejemplo de uso:** Evaluar el impacto de desmantelar un laboratorio desechable.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/plan

> Pendiente de validación en laboratorio.

## `terraform graph -type=plan`

```bash
terraform graph -type=plan
```

- **Sirve para:** Generar el grafo de dependencias de planificación en formato DOT para analizarlo.
- **Parámetros:** `graph`: genera DOT; `-type=plan`: incluye operaciones de planificación; sin cambios remotos.
- **Ejemplo de uso:** Analizar dependencias entre módulos y recursos antes de cambios.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/graph

> Pendiente de validación en laboratorio.
