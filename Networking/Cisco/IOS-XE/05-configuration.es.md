---
tags: [cli, cisco, ios-xe, configuration]
vendor: Cisco
os: "IOS XE"
validation: not-lab-verified
---

# ⚙️ Configuración general

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS XE · **Versiones de referencia:** IOS XE 17.x. Confirma el comando en tu versión instalada.

## Cambiar hostname

```text
configure terminal
hostname RTR-LAB
end
```

- **Sirve para:** Cambia el nombre del dispositivo.
- **Parámetros:** configure terminal: entrar a configuración; hostname: nombre; end: salir.
- **Ejemplo de uso:** Identificar un router de laboratorio.

- **Verificación:** `show running-config | include ^hostname` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## Configurar Loopback0

```text
configure terminal
interface Loopback0
 ip address 192.0.2.1 255.255.255.255
end
```

- **Sirve para:** Crea una loopback con IPv4 /32.
- **Parámetros:** interface Loopback0: interfaz virtual; ip address: IP y máscara.
- **Ejemplo de uso:** Usar una IP estable en un laboratorio.

- **Verificación:** `show ip interface brief | include Loopback0` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## Agregar ruta estática

```text
configure terminal
ip route 198.51.100.0 255.255.255.0 192.0.2.254
end
```

- **Sirve para:** Instala una ruta estática IPv4.
- **Parámetros:** ip route: destino, máscara, siguiente salto.
- **Ejemplo de uso:** Llegar a otra red del laboratorio.
- **Precaución:** Verifica que el siguiente salto sea alcanzable.

- **Verificación:** `show ip route 198.51.100.10` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## Configurar buffer de logs

```text
configure terminal
logging buffered 16384
end
```

- **Sirve para:** Habilita un buffer de logs en memoria.
- **Parámetros:** 16384: tamaño en bytes (los límites varían según equipo).
- **Ejemplo de uso:** Revisar eventos con show logging.

- **Verificación:** `show running-config | include logging buffered` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## Configurar timestamps

```text
configure terminal
service timestamps log datetime msec
end
```

- **Sirve para:** Agrega fecha/hora con milisegundos a los logs.
- **Parámetros:** log: mensajes syslog; datetime: fecha/hora; msec: milisegundos.
- **Ejemplo de uso:** Correlacionar eventos por hora.

- **Verificación:** `show running-config | include service timestamps` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Sirve para:** Guarda la configuración activa.
- **Parámetros:** running-config: origen; startup-config: destino guardado.
- **Ejemplo de uso:** Conservar cambios validados tras reiniciar.
- **Precaución:** Guarda únicamente cambios que deseas conservar.

- **Verificación:** `show running-config | include ^hostname|^ip route` — Filtra o verifica información relevante; consulta la salida completa cuando necesites contexto.


> Referencia breve, no validada en laboratorio. Valida con la ayuda de la CLI y documentación del modelo/release.

**Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/routers/access/isr1100/software/configuration/xe-17/isr1100-sw-config-xe-17/using_iosxe_software.pdf · https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/configuration/15-mt/ir-15-mt-book/ir-cfg-vir-if.html · https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
