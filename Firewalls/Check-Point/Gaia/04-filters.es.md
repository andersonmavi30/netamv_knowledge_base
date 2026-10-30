---
tags: [cli, check-point, gaia, filters]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Filtros de salida

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Expert (Bash). Confirma versión R8x y rol antes de ejecutar.

## `clish -c "show configuration" | grep "static-route"`

```text
clish -c "show configuration" | grep "static-route"
```

- **Sirve para:** Encuentra rutas estáticas en configuración.
- **Parámetros:** -c: comando Clish; grep: líneas coincidentes.
- **Ejemplo de uso:** Auditar rutas estáticas.

## `clish -c "show version all" | grep -i kernel`

```text
clish -c "show version all" | grep -i kernel
```

- **Sirve para:** Filtra información de kernel.
- **Parámetros:** grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Verificar versión base.

## `tail -n 100 /var/log/messages | grep -i error`

```text
tail -n 100 /var/log/messages | grep -i error
```

- **Sirve para:** Busca errores en los últimos 100 logs.
- **Parámetros:** -n 100: últimas 100 líneas; grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Buscar alarmas recientes.

## `clish -c "show interfaces all" | grep -i "down"`

```text
clish -c "show interfaces all" | grep -i "down"
```

- **Sirve para:** Encuentra interfaces down.
- **Parámetros:** grep -i: filtra texto sin mayúsculas.
- **Ejemplo de uso:** Detectar caída de uplink.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-Expert-Mode.htm)
