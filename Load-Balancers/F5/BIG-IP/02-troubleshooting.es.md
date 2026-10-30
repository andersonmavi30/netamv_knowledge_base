---
tags: [cli, f5, big-ip, tmos, troubleshooting]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash (tmsh prefix). Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tmsh show ltm virtual /Common/lab_vs`

```text
tmsh show ltm virtual /Common/lab_vs
```

- **Sirve para:** Consulta estado y tráfico de VIP.
- **Parámetros:** /Common/lab_vs: ruta del objeto.
- **Ejemplo de uso:** Determinar por qué VIP está offline.

## `tmsh show ltm pool /Common/lab_pool`

```text
tmsh show ltm pool /Common/lab_pool
```

- **Sirve para:** Consulta salud del pool.
- **Parámetros:** /Common/lab_pool: pool específico.
- **Ejemplo de uso:** Localizar pool sin miembros sanos.

## `tmsh show sys connection cs-client-addr 192.0.2.10`

```text
tmsh show sys connection cs-client-addr 192.0.2.10
```

- **Sirve para:** Busca conexiones activas de cliente.
- **Parámetros:** cs-client-addr: filtro IP cliente.
- **Ejemplo de uso:** Confirmar peticiones a TMM.

## `tmsh show ltm node /Common/192.0.2.20`

```text
tmsh show ltm node /Common/192.0.2.20
```

- **Sirve para:** Consulta nodo backend.
- **Parámetros:** node: dirección de ejemplo.
- **Ejemplo de uso:** Investigar backend fallido.

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/modules/ltm/ltm_pool.html) · [2](https://clouddocs.f5.com/cli/tmsh-reference/latest/modules/ltm/ltm_virtual.html)
