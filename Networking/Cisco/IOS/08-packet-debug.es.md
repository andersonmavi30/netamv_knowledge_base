---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Captura y depuración — Cisco IOS

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** Classic IOS (EPC supported only on certain platforms/trains).

> ⚠️ Captura y debug pueden generar carga o datos sensibles. Utilízalos solo en entornos autorizados, con filtros y límites; detén al finalizar.

## monitor capture buffer LABBUF size 256 max-size 100 circular

```text
monitor capture buffer LABBUF size 256 max-size 100 circular
monitor capture point ip cef LABPOINT FastEthernet0/0 both
monitor capture point associate LABPOINT LABBUF
monitor capture point start LABPOINT
```

- **Sirve para:** Inicia captura EPC limitada cuando IOS clásico la admite.
- **Parámetros:** size 256: búfer KB; max-size 100: bytes por paquete; both: ambas direcciones; associate: vincula búfer.
- **Caso real:** Diagnosticar paquetes en una interfaz FastEthernet de laboratorio; validar disponibilidad con `?`.

## monitor capture point stop LABPOINT

```text
monitor capture point stop LABPOINT
show monitor capture buffer LABBUF dump
no monitor capture point ip cef LABPOINT FastEthernet0/0 both
no monitor capture buffer LABBUF
```

- **Sirve para:** Detiene, consulta y elimina una captura EPC IOS.
- **Parámetros:** stop: detiene; dump: bytes de paquetes; no: elimina captura.
- **Caso real:** Liberar recursos al terminar una prueba breve.

## debug ip ospf adj

```text
debug ip ospf adj
undebug all
```

- **Sirve para:** Consulta eventos de adyacencias OSPF brevemente; luego detén el debug.
- **Parámetros:** adj: depura adyacencias; undebug all: detiene todos los debug.
- **Caso real:** Diagnosticar vecino que no llega a FULL.

**Referencia del fabricante:** https://www.cisco.com/c/en/us/support/docs/ios-nx-os-software/ios-embedded-packet-capture/116045-productconfig-epc-00.html

**Aviso:** no todos los equipos soportan sniffer/EPC en hardware de forwarding. Debug de protocolos no equivale a PCAP.
