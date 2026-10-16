---
tags: [cli, packet-capture, debugging]
validation: not-lab-verified
---

# 🧪 Captura y depuración — Huawei VRP

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Versión orientativa:** VRP generic (verify product/release).

> ⚠️ Captura y debug pueden generar carga o datos sensibles. Utilízalos solo en entornos autorizados, con filtros y límites; detén al finalizar.

## debugging ospf packet hello interface GigabitEthernet1/0/0

```text
debugging ospf packet hello interface GigabitEthernet1/0/0
terminal monitor
terminal debugging
```

- **Sirve para:** Observa temporalmente Hellos OSPF y depuración en terminal en plataformas compatibles.
- **Parámetros:** hello: paquetes Hello; interface: limita alcance; terminal debugging: muestra debug.
- **Caso real:** Revisar por qué vecinos OSPF no llegan a FULL.

## undo debugging ospf packet

```text
undo debugging ospf packet
undo terminal debugging
undo terminal monitor
```

- **Sirve para:** Detiene debug OSPF y mensajes en la terminal.
- **Parámetros:** undo: desactiva la opción indicada.
- **Caso real:** Evitar dejar debug activo consumiendo recursos.

## display logbuffer | include DOWN

```text
display logbuffer | include DOWN
```

- **Sirve para:** Busca eventos en logs; no captura paquetes completos.
- **Parámetros:** include: filtra texto, no paquetes.
- **Caso real:** Ver alarmas de interfaces antes de usar un método de mirroring compatible.

**Referencia del fabricante:** https://info.support.huawei.com/network/ptmngsys/Web/tsrev_ne/en/content/ne/21_edesk_ne_ospf_peer_status_is_abnormal/edesk_ne_ospf_peer_status_is_abnormal_edesk002.html

**Aviso:** no todos los equipos soportan sniffer/EPC en hardware de forwarding. Debug de protocolos no equivale a PCAP.
