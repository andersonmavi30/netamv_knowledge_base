---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Captura y depuración — MikroTik RouterOS

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** RouterOS 7.x (sniffer availability depends on device-mode).

> ⚠️ Captura y debug pueden generar carga o datos sensibles. Utilízalos solo en entornos autorizados, con filtros y límites; detén al finalizar.

## /tool sniffer quick filter-interface=ether1 filter-ip-address=192.0.2.10

```text
/tool sniffer quick filter-interface=ether1 filter-ip-address=192.0.2.10
```

- **Sirve para:** Captura en vivo por interfaz e IP. Detén con Ctrl+C.
- **Parámetros:** quick: en vivo; filter-interface: interfaz; filter-ip-address: IP.
- **Caso real:** Comprobar tráfico de un host de laboratorio en ether1.

## /tool sniffer quick filter-interface=ether1 filter-port=443

```text
/tool sniffer quick filter-interface=ether1 filter-port=443
```

- **Sirve para:** Observa paquetes por puerto TCP/UDP 443.
- **Parámetros:** filter-port: busca puerto; quick: captura interactiva.
- **Caso real:** Encontrar tráfico HTTPS sin revisar todos los paquetes.

## /tool sniffer set filter-interface=ether1 filter-ip-protocol=icmp file-name=lab-capture.pcap file-limit=1000KiB

```text
/tool sniffer set filter-interface=ether1 filter-ip-protocol=icmp file-name=lab-capture.pcap file-limit=1000KiB
/tool sniffer start
/tool sniffer stop
```

- **Sirve para:** Guarda una captura limitada en archivo para análisis posterior.
- **Parámetros:** file-name: archivo; file-limit: tamaño máximo; stop: termina.
- **Caso real:** Analizar ICMP en Wireshark; confirma formato del archivo según RouterOS.

## /system device-mode print

```text
/system device-mode print
```

- **Sirve para:** Comprueba si device-mode permite capturar tráfico.
- **Parámetros:** print: estado de funciones.
- **Caso real:** Entender 'not allowed by device-mode' sin modificar configuración.

**Referencia del fabricante:** https://help.mikrotik.com/docs/spaces/ROS/pages/8323088/Packet%20Sniffer

**Aviso:** no todos los equipos soportan sniffer/EPC en hardware de forwarding. Debug de protocolos no equivale a PCAP.
