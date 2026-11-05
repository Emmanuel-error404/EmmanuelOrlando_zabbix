# Configuraciones del laboratorio

Los archivos R1_running-config.txt y SW1_running-config.txt contienen las configuraciones suministradas por el autor. Se retiraron únicamente los mensajes y prompts de la consola. Se conservaron las opciones del equipo y los banners del switch.

La comunidad SNMP mostrada es la utilizada en el laboratorio aislado y tiene permiso RO.

## Recreación de la VLAN

En este switch la declaración de VLAN 10 no aparece en la salida de running-config. Al recrear el laboratorio en un equipo limpio, crear la VLAN antes de configurar sus puertos y su SVI:

```text
enable
configure terminal
vlan 10
 name LAN
exit
end
```

El nombre LAN es una etiqueta para la recreación. La evidencia confirma el uso de VLAN 10; no se recibió una exportación de vlan.dat ni de show vlan brief.

Tras cargar las configuraciones, comprobar interfaces activas, conectividad y guardar con `copy running-config startup-config`.

El servidor utiliza Zabbix Appliance 7.0.32 con DHCP. No utiliza el Netplan propuesto inicialmente para Ubuntu y no se incluye una configuración de red inventada del appliance.
