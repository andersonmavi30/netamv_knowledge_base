---
tags: [cli, f5, big-ip, tmos, operations]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Operación LTM

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash (tmsh prefix). Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tmsh show ltm pool /Common/lab_pool members`

```text
tmsh show ltm pool /Common/lab_pool members
```

- **Sirve para:** Consulta estado de todos los miembros.
- **Parámetros:** members: estado por miembro.
- **Ejemplo de uso:** Encontrar backend offline.

## `tmsh show ltm virtual /Common/lab_vs detail`

```text
tmsh show ltm virtual /Common/lab_vs detail
```

- **Sirve para:** Consulta contadores detallados de VIP.
- **Parámetros:** detail: estadísticas ampliadas.
- **Ejemplo de uso:** Investigar tasa de solicitudes.

## `tmsh list ltm virtual /Common/lab_vs profiles`

```text
tmsh list ltm virtual /Common/lab_vs profiles
```

- **Sirve para:** Consulta perfiles TCP/HTTP/SSL.
- **Parámetros:** profiles: colección de perfiles.
- **Ejemplo de uso:** Verificar perfil requerido.

## `tmsh show cm traffic-group`

```text
tmsh show cm traffic-group
```

- **Sirve para:** Consulta estado del grupo failover.
- **Parámetros:** cm traffic-group: grupos flotantes.
- **Ejemplo de uso:** Validar rol HA antes de mantenimiento.

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://clouddocs.f5.com/cli/tmsh-reference/latest/modules/ltm/ltm_virtual.html)
