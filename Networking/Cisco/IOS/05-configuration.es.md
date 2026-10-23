---
tags: [cli, cisco, ios, configuration]
vendor: Cisco
os: "IOS"
validation: not-lab-verified
---

# ⚙️ Configuración general

[🇬🇧 English](05-configuration.md) · [🇨🇴 Español](05-configuration.es.md) · [↩ Cisco](../README.es.md)

**Plataforma:** Cisco / IOS · **Versiones de referencia:** IOS 15.x (classic; feature availability varies). Confirma el comando en tu versión instalada.

## Cambiar hostname

```text
configure terminal
hostname RTR-LAB
end
```

**Validar con:**

```text
show running-config | include ^hostname
```


- **Sirve para:** Cambia el nombre del dispositivo.
- **Parámetros:** configure terminal: entrar a configuración; hostname: nombre; end: salir.
- **Ejemplo de uso:** Identificar un router de laboratorio.

- **Verificación:** `show running-config | include ^hostname` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## Configurar Loopback0

```text
configure terminal
interface Loopback0
 ip address 192.0.2.1 255.255.255.255
end
```

**Validar con:**

```text
show ip interface brief | include Loopback0
```


- **Sirve para:** Crea una loopback con IPv4 /32.
- **Parámetros:** interface Loopback0: interfaz virtual; ip address: IP y máscara.
- **Ejemplo de uso:** Usar una IP estable en un laboratorio.

- **Verificación:** `show ip interface brief | include Loopback0` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## Agregar ruta estática

```text
configure terminal
ip route 198.51.100.0 255.255.255.0 192.0.2.254
end
```

**Validar con:**

```text
show ip route 198.51.100.10
```


- **Sirve para:** Instala una ruta estática IPv4.
- **Parámetros:** ip route: destino, máscara, siguiente salto.
- **Ejemplo de uso:** Llegar a otra red del laboratorio.
- **Precaución:** Verifica que el siguiente salto sea alcanzable.

- **Verificación:** `show ip route 198.51.100.10` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## Configurar buffer de logs

```text
configure terminal
logging buffered 16384
end
```

**Validar con:**

```text
show running-config | include logging buffered
```


- **Sirve para:** Habilita un buffer de logs en memoria.
- **Parámetros:** 16384: tamaño en bytes (los límites varían según equipo).
- **Ejemplo de uso:** Revisar eventos con show logging.

- **Verificación:** `show running-config | include logging buffered` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## Configurar timestamps

```text
configure terminal
service timestamps log datetime msec
end
```

**Validar con:**

```text
show running-config | include service timestamps
```


- **Sirve para:** Agrega fecha/hora con milisegundos a los logs.
- **Parámetros:** log: mensajes syslog; datetime: fecha/hora; msec: milisegundos.
- **Ejemplo de uso:** Correlacionar eventos por hora.

- **Verificación:** `show running-config | include service timestamps` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.

## `copy running-config startup-config`

```text
copy running-config startup-config
```

- **Sirve para:** Guarda la configuración activa.
- **Parámetros:** running-config: origen; startup-config: destino guardado.
- **Ejemplo de uso:** Conservar cambios validados tras reiniciar.
- **Precaución:** Guarda únicamente cambios que deseas conservar.

- **Verificación:** `show running-config | include ^hostname|^ip route` — Filtra o verifica únicamente la información relevante; consulta la salida completa si necesitas contexto.


> Referencia breve, no validada en laboratorio. Valida con la ayuda de la CLI y documentación del modelo/release.

**Referencia oficial:** https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/interface/configuration/15-mt/ir-15-mt-book/ir-cfg-vir-if.html · https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/iproute_pi/configuration/15-mt/iri-15-mt-book/iri-iprouting.html
