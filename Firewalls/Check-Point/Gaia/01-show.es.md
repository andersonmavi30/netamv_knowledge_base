---
tags: [cli, check-point, gaia, show]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Expert → clish. Confirma versión R8x y rol antes de ejecutar.

## `clish -c "show version all" | grep -i "Product version"`

```text
clish -c "show version all" | grep -i "Product version"
```

- **Sirve para:** Identifica la versión Gaia.
- **Parámetros:** -c: ejecuta Clish; grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Verificar sistema antes del mantenimiento.

## `clish -c "show hostname"`

```text
clish -c "show hostname"
```

- **Sirve para:** Muestra el nombre actual.
- **Parámetros:** -c: ejecuta comando Clish.
- **Ejemplo de uso:** Identificar firewall conectado por SSH.

## `clish -c "show uptime"`

```text
clish -c "show uptime"
```

- **Sirve para:** Consulta tiempo encendido.
- **Parámetros:** -c: obtiene salida Gaia Clish.
- **Ejemplo de uso:** Investigar reinicio reciente.

## `clish -c "show version os kernel"`

```text
clish -c "show version os kernel"
```

- **Sirve para:** Consulta versión del kernel.
- **Parámetros:** os kernel: versión específica de kernel.
- **Ejemplo de uso:** Comparar nodos durante auditoría.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-Expert-Mode.htm)
