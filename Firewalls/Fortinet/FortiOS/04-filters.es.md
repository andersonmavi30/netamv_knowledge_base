---
tags: [cli, fortinet, fortios, filters]
vendor: Fortinet
os: "FortiOS"
validation: not-lab-verified
---

# 🔍 Filtros de salida

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Fortinet](../README.es.md)

**Plataforma:** Fortinet / FortiOS · **Compatibilidad:** FortiOS 7.x (comprueba tu versión exacta).

## `get system status | grep Version`

```text
get system status | grep Version
```

- **Sirve para:** Muestra líneas que contienen Version.
- **Parámetros:** |: tubería; grep: búsqueda de texto.
- **Ejemplo de uso:** Localizar versión de firmware.

- **Filtro práctico:** `get system status | grep -i hostname` — Ejemplo real: busca el hostname sin distinguir mayúsculas.

## `get system status | grep -i hostname`

```text
get system status | grep -i hostname
```

- **Sirve para:** Busca sin distinguir mayúsculas/minúsculas.
- **Parámetros:** -i: ignora mayúsculas/minúsculas.
- **Ejemplo de uso:** Buscar el hostname sin importar mayúsculas.

- **Filtro práctico:** `get system status | grep -i version` — Busca la versión del firmware con -i.

## `show system interface | grep -f port3`

```text
show system interface | grep -f port3
```

- **Sirve para:** Muestra el bloque de configuración coincidente con contexto (si es compatible).
- **Parámetros:** -f: salida con contexto de configuración.
- **Ejemplo de uso:** Ubicar los ajustes de port3.

- **Filtro práctico:** `show firewall address | grep -f LAB-NET` — Conserva el contexto del objeto coincidente.

## `get system interface | grep -n port3`

```text
get system interface | grep -n port3
```

- **Sirve para:** Muestra coincidencias con número de línea.
- **Parámetros:** -n: numeración de líneas.
- **Ejemplo de uso:** Encontrar port3 en salidas extensas.

- **Filtro práctico:** `diagnose vpn tunnel list | grep -n name=` — Busca nombres de túneles con números de línea.


> **Nota:** Referencia rápida, no verificada en laboratorio; confirma sintaxis y permisos en tu modelo y versión.

**Fuente del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966

## `get system global | grep vdom-mode`

```text
get system global | grep vdom-mode
```

- **Sirve para:** Verificar el modo configurado de dominios virtuales.
- **Parámetros:** `get system global`: parámetros globales; `grep vdom-mode`: muestra campo relacionado.
- **Ejemplo de uso:** Confirmar multi-VDOM tras un cambio controlado.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.0/administration-guide/317358

> Pendiente de validación en laboratorio; confirmar contexto y respaldos.

## `get system performance status | grep Uptime`

```text
get system performance status | grep Uptime
```

- **Sirve para:** Extraer el tiempo encendido del FortiGate desde sus métricas.
- **Parámetros:** `performance status`: métricas del equipo; `grep Uptime`: filtra línea de uptime (sensible a mayúsculas).
- **Ejemplo de uso:** Relacionar una caída con un reinicio reciente.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-troubleshooting-cheat-sheet/420966

> Pendiente de validación en laboratorio; confirma versión.

## `show | grep -f FW_SITE_A`

```text
show | grep -f FW_SITE_A
```

- **Sirve para:** Encontrar un objeto o ajuste dentro del contexto de configuración actual incluyendo líneas relacionadas.
- **Parámetros:** `show`: contexto actual; `grep -f FW_SITE_A`: filtro FortiOS con contexto; verificar salida.
- **Ejemplo de uso:** Encontrar referencias a un objeto de dirección o política.
- **Referencia oficial:** https://docs.fortinet.com/document/fortigate/7.4.0/cli-reference

> Pendiente de validación en laboratorio; no publiques configuraciones, logs ni secretos.
