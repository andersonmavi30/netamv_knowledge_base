---
tags: [cli, palo-alto-networks, pan-os, troubleshooting]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🛠️ Diagnóstico

[🇬🇧 English](02-troubleshooting.md) · [🇨🇴 Español](02-troubleshooting.es.md) · [↩ Índice PAN-OS](README.es.md)

**Compatibilidad:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Buscar sesiones desde cliente

```text
show session all filter source 192.0.2.10
```

- **Sirve para:** Busca sesiones con esa IP origen usando filtros internos.
- **Parámetros y filtros:** filter source: filtra tabla por IP origen.
- **Caso real:** Comprobar si el cliente genera sesiones.

## Buscar tráfico hacia servidor TCP/443

```text
show session all filter destination 198.51.100.10 destination-port 443
```

- **Sirve para:** Limita sesiones a servidor y puerto de destino.
- **Parámetros y filtros:** destination: IP destino; destination-port: puerto TCP/UDP.
- **Caso real:** Diagnosticar fallo de acceso a aplicación HTTPS.
- **Precaución:** Destination-port por sí solo no asegura solo TCP; agrega protocol 6 cuando aplique.

## Investigar descartes dataplane

```text
show counter global filter severity drop delta yes
```

- **Sirve para:** Muestra contadores de drop desde la muestra anterior.
- **Parámetros y filtros:** severity drop: descartes; delta yes: delta desde muestra previa.
- **Caso real:** Correlacionar descartes con prueba de conectividad.
- **Precaución:** La primera muestra delta puede no ser representativa; repite el comando.

## Probar política de seguridad HTTPS

```text
test security-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
```

- **Sirve para:** Encuentra la regla de seguridad que coincide con la conexión TCP.
- **Parámetros y filtros:** from/to: zonas; source/destination: IP; destination-port: 443; protocol 6: TCP.
- **Caso real:** Encontrar por qué una regla bloquearía al cliente.
- **Precaución:** Una política basada en App-ID puede necesitar indicar application.

## Probar coincidencia de NAT

```text
test nat-policy-match from trust to untrust source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
```

- **Sirve para:** Predice qué regla NAT coincide con un flujo.
- **Parámetros y filtros:** from/to: zonas; source/destination: IP; protocol 6: TCP.
- **Caso real:** Revisar qué NAT aplicaría al HTTPS de laboratorio.

> Ejemplos orientativos pendientes de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-cheat-sheet-networking)
