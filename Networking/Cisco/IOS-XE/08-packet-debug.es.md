---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Captura y depuración — Cisco IOS XE

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** IOS XE (EPC supported on suitable hardware/release).

> ⚠️ Captura y debug pueden generar carga o datos sensibles. Utilízalos solo en entornos autorizados, con filtros y límites; detén al finalizar.

## monitor capture LAB interface GigabitEthernet0/0/1 both

```text
monitor capture LAB interface GigabitEthernet0/0/1 both
monitor capture LAB match ipv4 host 192.0.2.10 any
monitor capture LAB start
```

- **Sirve para:** Configura captura en una interfaz con filtro de host IPv4.
- **Parámetros:** both: ambos sentidos; match: filtro de captura; start: inicia.
- **Caso real:** Seguir paquetes desde un host de laboratorio (valida sintaxis de match).

## monitor capture LAB stop

```text
monitor capture LAB stop
show monitor capture LAB buffer brief
no monitor capture LAB
```

- **Sirve para:** Detiene captura, revisa resumen de paquetes y la elimina.
- **Parámetros:** stop: detiene; buffer brief: lista de paquetes; no: elimina captura.
- **Caso real:** Finalizar sin dejar captura activa.

## show monitor capture LAB parameter

```text
show monitor capture LAB parameter
```

- **Sirve para:** Comprueba parámetros EPC antes de capturar tráfico.
- **Parámetros:** parameter: interfaz, filtro y búfer configurados.
- **Caso real:** Verificar la interfaz y filtro de la captura.

**Referencia del fabricante:** https://www.cisco.com/c/en/us/support/docs/ios-nx-os-software/ios-embedded-packet-capture/116045-productconfig-epc-00.html

**Aviso:** no todos los equipos soportan sniffer/EPC en hardware de forwarding. Debug de protocolos no equivale a PCAP.
