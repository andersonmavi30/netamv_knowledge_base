---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🧭 VPN, políticas y operación

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice PAN-OS](README.es.md)

**Compatibilidad:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Consultar gateway IKE específico

```text
show vpn ike-sa gateway LAB-IKE
```

- **Sirve para:** Busca SAs de fase 1 por gateway.
- **Parámetros y filtros:** gateway: nombre configurado.
- **Caso real:** Investigar error de negociación de fase 1.

## Consultar SAs de túnel IPsec

```text
show vpn ipsec-sa tunnel LAB-IPSEC
```

- **Sirve para:** Busca SAs de fase 2 de un túnel.
- **Parámetros y filtros:** tunnel: túnel seleccionado.
- **Caso real:** Determinar si fase 2 está instalada.

## Consultar contadores de túnel VPN

```text
show vpn flow name LAB-IPSEC
```

- **Sirve para:** Consulta tráfico y estado del túnel IPsec.
- **Parámetros y filtros:** name: nombre de túnel.
- **Caso real:** Revisar si contadores cambian al enviar tráfico.

## Localizar regla de seguridad

```text
show running security-policy | match LAB-ALLOW-HTTPS
```

- **Sirve para:** Busca política de seguridad activa por nombre.
- **Parámetros y filtros:** match: coincide con texto de salida.
- **Caso real:** Comprobar que regla está en running.

## Revisar contador de regla

```text
show running rule-use hit-count vsys vsys1 rule-base security rules rule-name LAB-ALLOW-HTTPS
```

- **Sirve para:** Muestra coincidencias de una regla en versiones compatibles.
- **Parámetros y filtros:** vsys: sistema virtual; rule-name: nombre de política.
- **Caso real:** Verificar si regla recibe tráfico y no solo existe.
- **Precaución:** Algunas reglas requieren soporte/configuración de hit-count.

> Ejemplos orientativos pendientes de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
