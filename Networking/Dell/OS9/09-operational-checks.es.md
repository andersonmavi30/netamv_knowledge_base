---
tags: [cli, networking, operational-checks]
validation: not-lab-verified
---

# Verificaciones operativas adicionales — Dell OS9

[🇬🇧 English](09-operational-checks.md) · [🇨🇴 Español](09-operational-checks.es.md) · [↩ Índice](README.es.md)

**Compatibilidad:** OS9 / Force10, platform-specific. Confirma comando y flags con la ayuda contextual de tu versión.

## Vecinos LLDP

```text
show lldp neighbors | grep UPLINK
```

- **Sirve para:** Descubre dispositivos vecinos.
- **Parámetros / flags:** neighbors: vecinos LLDP.
- **Caso real:** Validar enlace físico.
- **Filtro / verificación:** `show lldp neighbors`

## Resumen de LAG

```text
show port-channel summary | grep Po
```

- **Sirve para:** Revisa estado de agregación donde aplique.
- **Parámetros / flags:** summary: resumen de miembros.
- **Caso real:** Buscar miembro suspendido.
- **Filtro / verificación:** `show port-channel summary`

## Resumen BGP

```text
show ip bgp summary | grep Idle
```

- **Sirve para:** Consulta sesiones BGP en equipos L3.
- **Parámetros / flags:** summary: vecinos resumidos.
- **Caso real:** Localizar vecino Idle.
- **Filtro / verificación:** `show ip bgp summary | grep Idle`

## Aprendizaje MAC

```text
show mac-address-table | grep 0011
```

- **Sirve para:** Muestra MAC L2 aprendidas en equipos compatibles.
- **Parámetros / flags:** Sin parámetros; sintaxis puede variar.
- **Caso real:** Identificar MAC en trunk.
- **Filtro / verificación:** `show mac-address-table`

## Vecinos OSPF

```text
show ip ospf neighbor | grep FULL
```

- **Sirve para:** Muestra adyacencias OSPF.
- **Parámetros / flags:** Sin parámetros; requiere OSPF.
- **Caso real:** Comprobar vecinos.
- **Filtro / verificación:** `show ip ospf neighbor`

> ⚠️ Referencia de laboratorio aún no probada; distintas plataformas Dell y Huawei pueden usar variantes de comandos.

[Referencia del fabricante](https://www.dell.com/support/home/en-us/products/networking)
