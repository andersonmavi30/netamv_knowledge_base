---
tags: [cli, f5, big-ip, tmos, packet-debug]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Captura y debug

[🇬🇧 English](08-packet-debug.md) · [🇨🇴 Español](08-packet-debug.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash / Advanced Shell. Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tcpdump -nni 0.0:nnn -s0 -c 25 'host 192.0.2.10 and tcp port 443'`

```text
tcpdump -nni 0.0:nnn -s0 -c 25 'host 192.0.2.10 and tcp port 443'
```

- **Sirve para:** Captura hasta 25 paquetes en TMM.
- **Parámetros:** -nn: numérico; -i: interfaz; -s0: paquete completo; -c: límite.
- **Ejemplo de uso:** Seguir cliente HTTPS.
- **Precaución:** Puede mostrar contenido sensible; 0.0:nnn no aplica a todos los contextos.

## `tcpdump -nni 0.0:nnn -s0 -c 50 -w /var/tmp/lab-https.pcap 'host 198.51.100.10 and port 443'`

```text
tcpdump -nni 0.0:nnn -s0 -c 50 -w /var/tmp/lab-https.pcap 'host 198.51.100.10 and port 443'
```

- **Sirve para:** Guarda paquetes filtrados en PCAP.
- **Parámetros:** -w: archivo; -c: cantidad; BPF: VIP/puerto.
- **Ejemplo de uso:** Analizar en Wireshark.
- **Precaución:** Restringir acceso y borrar tras revisar.

## `tcpdump -nni 0.0:nnn -c 20 'arp or icmp'`

```text
tcpdump -nni 0.0:nnn -c 20 'arp or icmp'
```

- **Sirve para:** Consulta ARP e ICMP en TMM.
- **Parámetros:** -c 20: captura limitada; BPF: arp/icmp.
- **Ejemplo de uso:** Investigar conectividad con gateway.

## `tmsh show sys connection cs-server-addr 192.0.2.20`

```text
tmsh show sys connection cs-server-addr 192.0.2.20
```

- **Sirve para:** Consulta conexiones hacia backend.
- **Parámetros:** cs-server-addr: IP servidor, si está soportado.
- **Ejemplo de uso:** Comparar conexiones y captura.
- **Precaución:** Verificar sintaxis con ayuda tmsh.

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://my.f5.com/manage/s/article/K000132760) · [2](https://clouddocs.f5.com/cli/tmsh-reference/v16/general/tmsh.html)
