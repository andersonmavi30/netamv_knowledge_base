---
tags: [cli, check-point, gaia, packet-debug]
vendor: Check Point
os: Gaia
validation: not-lab-verified
---

# Captura y debug

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Plataforma:** Check Point / Gaia + Security Gateway · **Entorno:** Expert. Confirma versión R8x y rol antes de ejecutar.

## `tcpdump -ni eth1 -c 20 'host 192.0.2.10 and tcp port 443'`

```text
tcpdump -ni eth1 -c 20 'host 192.0.2.10 and tcp port 443'
```

- **Sirve para:** Captura 20 paquetes HTTPS en eth1.
- **Parámetros:** -n: numérico; -i: interfaz; -c 20: límite; BPF: IP/puerto.
- **Ejemplo de uso:** Comprobar llegada de TLS.
- **Precaución:** Capturas pueden mostrar datos sensibles.

## `fw monitor -F "192.0.2.10,0,198.51.100.20,443,6" -ci 20 -co 20 -o /var/log/lab_fw.cap`

```text
fw monitor -F "192.0.2.10,0,198.51.100.20,443,6" -ci 20 -co 20 -o /var/log/lab_fw.cap
```

- **Sirve para:** Captura flujo TCP en puntos de inspección.
- **Parámetros:** -F: IP/puerto origen,destino,protocolo; -ci/-co: límites; -o: archivo.
- **Ejemplo de uso:** Localizar dónde se corta un flujo.
- **Precaución:** Captura corta y borra archivos tras revisar.

## `fw ctl zdebug + drop | grep 192.0.2.10`

```text
fw ctl zdebug + drop | grep 192.0.2.10
```

- **Sirve para:** Observa drops de cliente.
- **Parámetros:** zdebug + drop: debug kernel; grep: IP.
- **Ejemplo de uso:** Encontrar motivo de descarte.
- **Precaución:** Puede consumir CPU; detener con Ctrl+C.

## `tcpdump -ni eth1 -c 30 'udp port 500 or udp port 4500'`

```text
tcpdump -ni eth1 -c 30 'udp port 500 or udp port 4500'
```

- **Sirve para:** Captura IKE y NAT-T.
- **Parámetros:** -c 30: límite; UDP 500/4500: IKE/NAT-T.
- **Ejemplo de uso:** Confirmar negociación VPN en WAN.

> Comandos de referencia pendientes de validación práctica. Verifica permisos, modo Clish/Expert y versión.

**Documentación:** [1](https://sc1.checkpoint.com/documents/R82/WebAdminGuides/EN/CP_R82_CLI_ReferenceGuide/Content/Topics-CLIG/FWG/fw-monitor.htm) · [2](https://sc1.checkpoint.com/documents/SD-WAN-with-Smart1/Content/Topics-SD-WAN/13_Troubleshooting.htm)
