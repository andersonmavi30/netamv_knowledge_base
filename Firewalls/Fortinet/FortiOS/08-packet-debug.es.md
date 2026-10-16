---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Captura y depuración — Fortinet FortiOS

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** FortiOS 7.x.

> ⚠️ Captura y debug pueden generar carga o datos sensibles. Utilízalos solo en entornos autorizados, con filtros y límites; detén al finalizar.

## diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 a

```text
diagnose sniffer packet any 'host 192.0.2.10 and tcp port 443' 4 20 a
```

- **Sirve para:** Captura hasta 20 paquetes TCP/443 del host, mostrando interfaces.
- **Parámetros:** any: todas las interfaces; BPF: host/puerto; 4: cabecera e interfaz; 20: máximo; a: hora absoluta.
- **Caso real:** Identificar interfaces de entrada/salida en una conexión HTTPS fallida.

## diagnose sniffer packet any 'arp or icmp' 4 20 a

```text
diagnose sniffer packet any 'arp or icmp' 4 20 a
```

- **Sirve para:** Revisa ARP e ICMP con captura limitada.
- **Parámetros:** arp or icmp: alternativas BPF; 20: máximo.
- **Caso real:** Ver si ARP y ping llegan al firewall.

## diagnose debug disable

```text
diagnose debug disable
diagnose debug reset
```

- **Sirve para:** Detiene el debug y limpia filtros anteriores.
- **Parámetros:** disable: detiene depuración; reset: limpia opciones.
- **Caso real:** Dejar el firewall sin debug después del diagnóstico.

**Referencia del fabricante:** https://docs.fortinet.com/document/fortigate/7.4.0/administration-guide/680228/performing-a-sniffer-trace-cli-and-packet-capture

**Aviso:** no todos los equipos soportan sniffer/EPC en hardware de forwarding. Debug de protocolos no equivale a PCAP.
