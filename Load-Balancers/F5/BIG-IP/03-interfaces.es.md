---
tags: [cli, f5, big-ip, tmos, interfaces]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Interfaces y routing

[🇬🇧 English](03-interfaces.md) · [🇨🇴 Español](03-interfaces.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash (tmsh prefix). Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tmsh show net interface 1.1`

```text
tmsh show net interface 1.1
```

- **Sirve para:** Consulta interfaz física 1.1.
- **Parámetros:** 1.1: puerto de ejemplo en hardware compatible.
- **Ejemplo de uso:** Diagnosticar descartes.

## `tmsh list net self | grep 192.0.2`

```text
tmsh list net self | grep 192.0.2
```

- **Sirve para:** Busca Self IP por subred.
- **Parámetros:** net self: IP locales; grep: texto de subred.
- **Ejemplo de uso:** Verificar Self IP de VLAN de servidores.

## `tmsh list net vlan | grep -i external`

```text
tmsh list net vlan | grep -i external
```

- **Sirve para:** Identifica la VLAN externa.
- **Parámetros:** grep -i: ignora mayúsculas.
- **Ejemplo de uso:** Relacionar interfaz externa con VLAN.

## `tmsh show net route lookup 198.51.100.10`

```text
tmsh show net route lookup 198.51.100.10
```

- **Sirve para:** Consulta ruta a una IP destino.
- **Parámetros:** lookup: consulta ruta de una IP.
- **Ejemplo de uso:** Comprobar rutas a redes backend.

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v14/modules/net/net_route.html)
