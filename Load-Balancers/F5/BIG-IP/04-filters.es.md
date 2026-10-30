---
tags: [cli, f5, big-ip, tmos, filters]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Filtros de salida

[🇬🇧 English](04-filters.md) · [🇨🇴 Español](04-filters.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash (tmsh prefix). Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tmsh list ltm virtual | grep -i lab`

```text
tmsh list ltm virtual | grep -i lab
```

- **Sirve para:** Busca configuración de VIP por nombre.
- **Parámetros:** | grep -i: búsqueda sin mayúsculas.
- **Ejemplo de uso:** Encontrar VIP de aplicación.

## `tmsh show ltm pool | grep -i offline`

```text
tmsh show ltm pool | grep -i offline
```

- **Sirve para:** Busca líneas de pool offline.
- **Parámetros:** grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Encontrar pools afectados.
- **Precaución:** Consultar pool completo para estado real.

## `tmsh list ltm pool /Common/lab_pool | grep -A 8 members`

```text
tmsh list ltm pool /Common/lab_pool | grep -A 8 members
```

- **Sirve para:** Muestra miembros con contexto.
- **Parámetros:** -A 8: ocho líneas después de la coincidencia.
- **Ejemplo de uso:** Revisar lista de backends.

## `tmsh list ltm virtual | grep -i destination`

```text
tmsh list ltm virtual | grep -i destination
```

- **Sirve para:** Muestra destinos configurados de VIP.
- **Parámetros:** grep -i destination: coincide con campo.
- **Ejemplo de uso:** Encontrar IP/puertos VIP.

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/grep.html)
