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

## `terraform init -upgrade`

```bash
terraform init -upgrade
```

- **Sirve para:** Reinicializar y actualizar proveedores/módulos según las restricciones de versión.
- **Parámetros:** `init`: inicializa; `-upgrade`: selecciona versiones compatibles y puede modificar `.terraform.lock.hcl`.
- **Ejemplo de uso:** Actualizar dependencias de laboratorio en una rama y revisar cambios del lockfile.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/init

> Pendiente de validación en laboratorio.

## `terraform workspace list`

```bash
terraform workspace list
```

- **Sirve para:** Listar los workspaces CLI disponibles e identificar el seleccionado.
- **Parámetros:** `workspace list`: lista workspaces; `*` indica el activo; no modifica selección.
- **Ejemplo de uso:** Comprobar el entorno seleccionado antes de planificar cambios de red.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/workspace/list

> Pendiente de validación en laboratorio.

## `terraform workspace show`

```bash
terraform workspace show
```

- **Sirve para:** Mostrar el nombre del workspace CLI de Terraform seleccionado.
- **Parámetros:** `workspace show`: muestra el nombre del workspace activo; sin flags.
- **Ejemplo de uso:** Verificar que el workspace activo corresponda al laboratorio desde un script.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/workspace/show

> Pendiente de validación en laboratorio.

## `terraform console`

```bash
terraform console
```

- **Sirve para:** Abrir una consola interactiva para evaluar expresiones, valores y funciones de Terraform.
- **Parámetros:** `console`: consola interactiva de expresiones; salir con `exit` o Ctrl-D; puede leer valores sensibles.
- **Ejemplo de uso:** Probar `cidrsubnet` u otras expresiones antes de definir subredes de red.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/console

> Pendiente de validación en laboratorio.

## `terraform workspace select lab`

```bash
terraform workspace select lab
```

- **Sirve para:** Seleccionar un workspace CLI existente para las siguientes operaciones de Terraform.
- **Parámetros:** `workspace select`: cambia el workspace activo; `lab`: workspace de ejemplo que debe existir; cambia selección local, no recursos remotos.
- **Ejemplo de uso:** Seleccionar el entorno de laboratorio y verificarlo con `terraform workspace show` antes de planificar.
- **Referencia oficial:** https://developer.hashicorp.com/terraform/cli/commands/workspace/select

> Pendiente de validación en laboratorio.
