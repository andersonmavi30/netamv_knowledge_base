---
tags: [cli, palo-alto-networks, pan-os, operations]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# VPN, políticas y operación

[🇬🇧 English](06-operations.md) · [🇨🇴 Español](06-operations.es.md) · [↩ Índice PAN-OS](README.es.md)

**Plataforma:** Palo Alto Networks / PAN-OS · **Compatibilidad:** confirma la versión instalada con `show system info | match sw-version`. Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## `show vpn ike-sa gateway LAB-IKE`

```text
show vpn ike-sa gateway LAB-IKE
```

- **Sirve para:** Busca SAs de fase 1 por gateway.
- **Parámetros:** gateway: nombre configurado.
- **Ejemplo de uso:** Investigar error de negociación de fase 1.

## `show vpn ipsec-sa tunnel LAB-IPSEC`

```text
show vpn ipsec-sa tunnel LAB-IPSEC
```

- **Sirve para:** Busca SAs de fase 2 de un túnel.
- **Parámetros:** tunnel: túnel seleccionado.
- **Ejemplo de uso:** Determinar si fase 2 está instalada.

## `show vpn flow name LAB-IPSEC`

```text
show vpn flow name LAB-IPSEC
```

- **Sirve para:** Consulta tráfico y estado del túnel IPsec.
- **Parámetros:** name: nombre de túnel.
- **Ejemplo de uso:** Revisar si contadores cambian al enviar tráfico.

## `show running security-policy | match LAB-ALLOW-HTTPS`

```text
show running security-policy | match LAB-ALLOW-HTTPS
```

- **Sirve para:** Busca política de seguridad activa por nombre.
- **Parámetros:** match: coincide con texto de salida.
- **Ejemplo de uso:** Comprobar que regla está en running.

## `show running rule-use hit-count vsys vsys1 rule-base security rules rule-name LAB-ALLOW-HTTPS`

```text
show running rule-use hit-count vsys vsys1 rule-base security rules rule-name LAB-ALLOW-HTTPS
```

- **Sirve para:** Muestra coincidencias de una regla en versiones compatibles.
- **Parámetros:** vsys: sistema virtual; rule-name: nombre de política.
- **Ejemplo de uso:** Verificar si regla recibe tráfico y no solo existe.
- **Precaución:** Algunas reglas requieren soporte/configuración de hit-count.

> Referencia breve, pendiente de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
