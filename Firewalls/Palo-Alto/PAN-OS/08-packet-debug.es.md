---
tags: [cli, palo-alto-networks, pan-os, packet-debug]
vendor: Palo Alto Networks
os: PAN-OS
validation: not-lab-verified
---

# 🧪 Sniffer, captura y debug

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice PAN-OS](README.es.md)

**Compatibilidad:** PAN-OS (revisar versión exacta con `show system info | match sw-version`). Los comandos pueden variar según versión, plataforma, vsys y modo de routing.

## Aplicar filtro por IP y puerto

```text
debug dataplane packet-diag set filter match source 192.0.2.10 destination 198.51.100.10 destination-port 443 protocol 6
debug dataplane packet-diag set filter on
```

- **Sirve para:** Activa filtro para flujo TCP específico.
- **Parámetros y filtros:** source/destination: IP; destination-port: 443; protocol 6: TCP; on: activa.
- **Caso real:** Investigar HTTPS sin capturar todo.
- **Precaución:** Usar solo tráfico autorizado y limitar captura.

## Limitar capturas en receive y drop

```text
debug dataplane packet-diag set capture stage receive file pan-rx.pcap packet-count 100
debug dataplane packet-diag set capture stage drop file pan-drop.pcap packet-count 100
```

- **Sirve para:** Configura archivos PCAP de recepción y descartes.
- **Parámetros y filtros:** stage: etapa de procesamiento; file: nombre; packet-count: límite.
- **Caso real:** Comprobar si el firewall recibe paquetes pero los descarta.

## Iniciar captura breve

```text
debug dataplane packet-diag show setting
debug dataplane packet-diag set capture on
```

- **Sirve para:** Revisa filtros y luego inicia recolección.
- **Parámetros y filtros:** show setting: revisa parámetros; capture on: inicia.
- **Caso real:** Capturar conexión breve desde cliente de laboratorio.
- **Precaución:** Capturas consumen recursos; detener enseguida.

## Detener captura y filtros

```text
debug dataplane packet-diag set capture off
debug dataplane packet-diag set filter off
```

- **Sirve para:** Detiene captura y filtro.
- **Parámetros y filtros:** capture off: detiene PCAP; filter off: deshabilita filtro.
- **Caso real:** Finalizar diagnóstico sin captura activa.

## Diagnosticar drops de flujo

```text
show counter global filter severity drop delta yes
```

- **Sirve para:** Revisa contadores de drops durante prueba.
- **Parámetros y filtros:** severity drop: contadores de descarte; delta yes: cambios incrementales.
- **Caso real:** Investigar pérdidas mientras capturas HTTPS.
- **Precaución:** Se recomienda medir delta más de una vez y en pruebas puntuales.

> Ejemplos orientativos pendientes de validación en laboratorio. Comprueba la ayuda contextual `?`, el contexto operational (`>`) y configuration (`#`) antes de ejecutarlos.

**Referencias oficiales:** [Guía 1](https://docs.paloaltonetworks.com/ngfw/administration/monitoring/take-packet-captures) · [Guía 2](https://docs.paloaltonetworks.com/ngfw/pan-os-cli-quick-start/cli-command-hierarchy/pan-os-11-2-cli-ops-command-hierarchy)
