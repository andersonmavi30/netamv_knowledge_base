---
tags: [cli, f5, big-ip, tmos, configuration]
vendor: F5
os: BIG-IP TMOS
validation: not-lab-verified
---

# Configuración

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Índice](README.es.md)

**Plataforma:** F5 BIG-IP / TMOS · **Contexto:** Bash (tmsh prefix). Versiones y módulos varían; confirmar con `tmsh show sys version`.

## `tmsh create ltm pool /Common/lab_pool members add { 192.0.2.20:80 192.0.2.21:80 } monitor http`

```text
tmsh create ltm pool /Common/lab_pool members add { 192.0.2.20:80 192.0.2.21:80 } monitor http
```

- **Sirve para:** Crea pool con monitoreo HTTP.
- **Parámetros:** members add: servidores; monitor http: chequeo.
- **Ejemplo de uso:** Preparar dos backends HTTP.
- **Precaución:** Probar conectividad y monitor antes de usar.

## `tmsh create ltm virtual /Common/lab_vs destination 198.51.100.10:80 pool /Common/lab_pool ip-protocol tcp source-address-translation { type automap }`

```text
tmsh create ltm virtual /Common/lab_vs destination 198.51.100.10:80 pool /Common/lab_pool ip-protocol tcp source-address-translation { type automap }
```

- **Sirve para:** Crea servidor virtual HTTP.
- **Parámetros:** destination: VIP:puerto; pool: backend; automap: SNAT.
- **Ejemplo de uso:** Publicar HTTP de laboratorio.
- **Precaución:** Creación impacta tráfico de inmediato; usar laboratorio.

## `tmsh list ltm virtual /Common/lab_vs`

```text
tmsh list ltm virtual /Common/lab_vs
```

- **Sirve para:** Consulta configuración de VIP.
- **Parámetros:** list: configuración.
- **Ejemplo de uso:** Revisar destino y pool antes de guardar.

## `tmsh save sys config`

```text
tmsh save sys config
```

- **Sirve para:** Guarda configuración aprobada.
- **Parámetros:** save: guarda running.
- **Ejemplo de uso:** Conservar cambios tras reinicio.

> Referencia sin validación de laboratorio. Algunos comandos requieren módulos LTM, HA o privilegios Bash; no todas las versiones son iguales.

**Documentación oficial:** [1](https://clouddocs.f5.com/training/community/f5cert/html/class8/module01/lab1.html)
