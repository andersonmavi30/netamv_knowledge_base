---
tags: [cli, palo-alto-networks, pan-os, troubleshooting]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice PAN-OS](README.es.md)

**Plataforma:** Palo Alto Networks / PAN-OS · **Compatibilidad:** confirma la versión instalada con `show system info | match sw-version`. Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## `show session all filter source 192.0.2.10`

```text
show session all filter source 192.0.2.10
```

- **Sirve para:** Busca sesiones con esa IP origen usando filtros internos.
- **Parámetros:** filter source: filtra tabla por IP origen.
- **Ejemplo de uso:** Comprobar si el cliente genera sesiones.

## `show session all filter destination 198.51.100.10 destination-port 443`

```text
show session all filter destination 198.51.100.10 destination-port 443
```

- **Sirve para:** Limita sesiones a servidor y puerto de destino.
- **Parámetros:** destination: IP destino; destination-port: puerto TCP/UDP.
- **Ejemplo de uso:** Diagnosticar fallo de acceso a aplicación HTTPS.
- **Precaución:** Destination-port por sí solo no asegura solo TCP; agrega protocol 6 cuando aplique.

## `show counter global filter severity drop delta yes`

```text
show counter global filter severity drop delta yes
```

- **Sirve para:** Muestra contadores de drop desde la muestra anterior.
- **Parámetros:** severity drop: descartes; delta yes: delta desde muestra previa.
- **Ejemplo de uso:** Correlacionar descartes con prueba de conectividad.
- **Precaución:** La primera muestra delta puede no ser representativa; repite el comando.

## `test security-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6`

```text
test security-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
```

- **Sirve para:** Encuentra la regla de seguridad que coincide con la conexión TCP.
- **Parámetros:** from/to: zonas; source/destination: IP; destination-port: 443; protocol 6: TCP.
- **Ejemplo de uso:** Encontrar por qué una regla bloquearía al cliente.
- **Precaución:** Una política basada en App-ID puede necesitar indicar application.

## `test nat-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6`

```text
test nat-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
```

- **Sirve para:** Predice qué regla NAT coincide con un flujo.
- **Parámetros:** from/to: zonas; source/destination: IP; protocol 6: TCP.
- **Ejemplo de uso:** Revisar qué NAT aplicaría al HTTPS de laboratorio.

> Referencia breve, pendiente de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking)
