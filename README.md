# Implementacion-Snort-Ubuntu

Objetivos de este proyecto
* Analizar los mecanismos de deteccion de intrusos en la red 
* implementar un sistema de deteccion de intrusos en la red
* Ejecutar configuraciones comunes en los sistemas de deteccion de intrusos
* Emplear y desarrollar mecanismos para detectar amenazas de red de forma proactiva.

### ¿Que es Snort?
![Untitled](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/0af78ee4a77c140d9cd4115f43079c24bfb6bc8f/img/1.PNG)

Es un sistema de prevencion de intrusiones de codigo abierto, basado en red, capaz de realizar analisis de trafico en tiempo real y registro de paquetes

### Caracteristicas de Snort

- Analisis d protocolos
- Deteccion de desbordamiento de bufer
- Deteccion de escaneos de puertos sigilosos
- Deteccion de ataques DOS
### modo de funcionamiento

- IDS o IPS  a nivel de red
- Basado en reglas
- Tiene tres usos primarios: Sniffer, Packet logger y NIDPS
![Untitled](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/6f3759c14ffd26e1c2aa2026dd14525fea7a6941/img/2.PNG)
### componentes de Snort

- decodificador
- pre-procesador
- motor de deteccion
- log

![Untitled](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/c4de5c9097351e9ba8a80ce30c3243fc3309ab09/img/3.PNG)

# inspectores (preprocesadores) en Snort

- esquema general
- tipos de inspectores
- Esquema de inspeccion de trafico en Snort 3

# Esquema general de los inspectores
![Untitled](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/e83e931958ccb8185e816170bda9712aa7384b99/img/4.PNG)

# Tipos de inspectores
| Tipo | Descripcion |
| --- | --- |
| Binder Inspector | determina cuando es necesario utilizar un servicio instpector para analizar el trafico |
| ARP Spoof Inspector | Decodifica los paquetes ARP y detecta solicitudes ARP de unidifusion y mapeo inconsistente de Ethernet a IP. |
| DCE Inspector (SMB y TCP) | Analiza, desfragmenta y normaliza los flujos de trafico de DCE/RPC encapsulados en SMB o TCP |
| FTP Inspector (Cliente y servidor) | Examina y normaliza los comandos en el canal de comandos FTP, determina la apertura de un canal de datos y cuando se encuentra cifrada una conexion. |
| HTTP Inspector | Proporciona inspeccion basada en PDU y normaliza los encabezados del trafico |
| IMAP Inspector | inspecciona el trafico IMAP3 de servidor a cliente decodificando comandos, encabezados, cuerpo y adjuntos |
| Normalizer Inspector | Normaliza el trafico para minimizar las tecnicas de evasion de deteccion |
| port Scan Inspector | Detecta Patrones de actividad para determinar cuales escaneos de puertos podiran considerarse maliciosos |
| Stream Inspector (ICMP,  IP, TCP, UDP ) | Proporciona seguimiento del flujo entre origen y destino, identificacion de sesion, Normalizacion y reensamblaje |
| telnet Inspector | Normaliza el bufer de datos con respecto a los comandos de telnet y negociacion de opciones. Determina cuando se cifra una conexion telnet |
| SSH Inspector | Detecta exploits CRC-32, direccion de mensaje incorrecta y desbordamiento de bufer |
| AppID | permite identificar y controlar trafico de aplicaciones o servicios |

### Esquema de inspeccion de trafico en Snort 3
![Untitled](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/9850ae27b88aaa1b81776397ef8e35c983ff3b08/img/5.PNG)

## Opciones y configuraciones de alertas en Snort
| Opcion | Descripcion |
| --- | --- |
| Fast | Envia la alerta en un formato simple con una marca de tiempo, mensaje de alerta, direccion de origen y de destino. |
| Full | Envia la alerta en un formato completo incluye los headers completos de los paquetes. |
| Unsock | Envia las alertas a un socket Unix que otro programa pueda escuchar. |
| None | Deshabilita las alertas. |
| Console  | Envia las alertas en formato simple hacia la consola. |
| CMG | Formato personalizado que muestra las alertas en formato full junto con el contenido del paquete. Este modo es solo para proposito de pruebas. |
| Syslog | Envia las alertas al servidor Syslog en formato fast. |

### Alertas en Snort

## orden por defecto de las alertas

la forma en la que snort aplicara las reglas es la siguiente:

- reglas permisivas
- reglas de descarte
- reglas de alertas
- reglas de logs

# Reordenamiento de alertas
| Opcion | Descripcion |
| --- | --- |
| —alert-before-pass | Fuerza a que las reglas de alertas se ejecuten antes de las reglas permisivas |
| —treat-drop-as-alert | Hace que las reglas de decarte o rechazo se ejecuten como alertas en vez de la accion predefinida. |
| —process-all-event | Hace que se procese cada evento asociado con un paquete, en base al orden de las reglas. |
