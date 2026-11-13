---
tags: [terraform, cli, netdevops, iac]
validation: not-lab-verified
---

# Conceptos básicos e inicialización

[🇬🇧 English](01-basics.md) · [🇨🇴 Español](01-basics.es.md) · [↩ Terraform](README.es.md)

**Plataforma:** Terraform CLI 1.x; ejemplos pendientes de prueba en laboratorio.

## `terraform version`

```bash
terraform version
```

- **Sirve para:** Mostrar versión instalada de Terraform y versiones de proveedores, si están disponibles.
- **Parámetros:** `version`: subcomando de consulta, sin flags ni cambios de infraestructura.
- **Ejemplo de uso:** Confirmar versión antes de inicializar un proyecto IaC.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/version

> Pendiente de validación en laboratorio.

## `terraform init -backend=false`

```bash
terraform init -backend=false
```

- **Sirve para:** Inicializar proveedores y módulos sin conectar el backend configurado.
- **Parámetros:** `init`: prepara directorio; `-backend=false`: omite inicialización del backend remoto.
- **Ejemplo de uso:** Preparar un módulo reutilizable para CI sin acceder al estado remoto.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/init

> Pendiente de validación en laboratorio.
