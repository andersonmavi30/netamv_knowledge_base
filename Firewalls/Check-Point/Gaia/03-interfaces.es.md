---
tags: [cli, check-point, gaia, interfaces]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Interfaces y routing

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Expert → clish. Confirma versión R8x y rol antes de ejecutar.

## `clish -c "show interface eth1"`

```text
clish -c "show interface eth1"
```

- **Sirve para:** Consulta interfaz física.
- **Parámetros:** eth1: interfaz de ejemplo.
- **Ejemplo de uso:** Revisar uplink.

## `clish -c "show interfaces all" | grep eth1`

```text
clish -c "show interfaces all" | grep eth1
```

- **Sirve para:** Filtra listado a una interfaz.
- **Parámetros:** all: todas; grep: texto.
- **Ejemplo de uso:** Buscar puerto sin revisar lista completa.

## `clish -c "show route all" | grep 198.51.100`

```text
clish -c "show route all" | grep 198.51.100
```

- **Sirve para:** Busca prefijo en tabla Gaia.
- **Parámetros:** route all: tabla; grep: filtro.
- **Ejemplo de uso:** Investigar subred remota ausente.

## `fw ctl iflist | grep eth1`

```text
fw ctl iflist | grep eth1
```

- **Sirve para:** Consulta interfaces vistas por kernel.
- **Parámetros:** iflist: interfaces kernel; grep: nombre.
- **Ejemplo de uso:** Comparar lista del kernel y Gaia.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_Gaia_AdminGuide/Content/Topics-GAG/Gaia-Clish-commands-for-network-interfaces.htm)
