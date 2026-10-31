---
tags: [cli, f5, big-ip, tmos, field-commands]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Verificaciones adicionales

[🇬🇧 English](07-field-commands.md) · [🇨🇴 Español](07-field-commands.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash (tmsh prefix). Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tmsh list sys ntp`

```text
tmsh list sys ntp
```

- **Sirve para:** Consulta servidores NTP.
- **Parámetros:** sys ntp: configuración NTP.
- **Ejemplo de uso:** Verificar precisión de hora.

## `tmsh list sys dns`

```text
tmsh list sys dns
```

- **Sirve para:** Consulta resolvers DNS.
- **Parámetros:** sys dns: DNS de administración.
- **Ejemplo de uso:** Diagnosticar problemas FQDN de monitores.

## `tmsh show sys version detail | grep -i hotfix`

```text
tmsh show sys version detail | grep -i hotfix
```

- **Sirve para:** Busca hotfix para mantenimiento.
- **Parámetros:** detail: versión extendida; grep -i: filtro.
- **Ejemplo de uso:** Comprobar versión tras parche.

## `tmsh list ltm monitor http | grep -i lab`

```text
tmsh list ltm monitor http | grep -i lab
```

- **Sirve para:** Busca monitores HTTP.
- **Parámetros:** list: configuración; grep -i: nombre.
- **Ejemplo de uso:** Auditar nombres de monitores.

## `tmsh show ltm persistence persist-records | grep 192.0.2.10`

```text
tmsh show ltm persistence persist-records | grep 192.0.2.10
```

- **Sirve para:** Busca registros de persistencia LTM correspondientes a una IP cliente.
- **Parámetros:** show ltm persistence persist-records: afinidades de persistencia; | grep: muestra coincidencias de IP.
- **Ejemplo de uso:** Investigar por qué un cliente sigue llegando al mismo backend después de cambios de balanceo.
- **Referencia oficial:** https://clouddocs.f5.com/training/community/adc/html/class7/modules/module02.html

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/tmsh.html)
