---
tags: [cli, f5, big-ip, tmos, show]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Consultas y estado

[🇬🇧 English](01-show.md) · [🇨🇴 Español](01-show.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash (tmsh prefix). Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tmsh show sys version | grep Version`

```text
tmsh show sys version | grep Version
```

- **Sirve para:** Muestra solo la versión BIG-IP.
- **Parámetros:** tmsh: consola; grep: línea coincidente.
- **Ejemplo de uso:** Verificar versión antes de cambiar.

## `tmsh show cm sync-status`

```text
tmsh show cm sync-status
```

- **Sirve para:** Consulta sincronización del grupo.
- **Parámetros:** cm sync-status: estado de sincronización.
- **Ejemplo de uso:** Encontrar equipo desincronizado.

## `tmsh list ltm virtual | grep -i lab_vs`

```text
tmsh list ltm virtual | grep -i lab_vs
```

- **Sirve para:** Busca nombre de servidor virtual.
- **Parámetros:** list: configuración; grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Ubicar VIP de laboratorio.

## `tmsh show sys performance system | grep -i cpu`

```text
tmsh show sys performance system | grep -i cpu
```

- **Sirve para:** Consulta datos CPU del sistema.
- **Parámetros:** show sys performance: recursos; grep -i: filtro.
- **Ejemplo de uso:** Investigar consumo de CPU.

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/tmsh.html) · [2](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/grep.html)
