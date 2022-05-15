# Creacion de reglas para snort

## ¿Qué es una regla en snort?
SNORT es un software NIDS de código abierto. 
Combinando los beneficios de la inspección basada en firmas, protocolos y anomalías, SNORT es la tecnología IDS / IPS más utilizada en todo el mundo.
Es capaz de realizar un "análisis de alto nivel" en todo el tráfico que fluye a través de su sensor.
# Reglas de snort
SNORT puede implementar cualquier tipo de regla, las reglas de SNORT no están incluidas con el software. Sin embargo,  
existen diferentes fuentes para encontrar e implementar reglas:
- **[Equipo de Investigación de Vulnerabilidad](https://en.wikipedia.org/wiki/Sourcefire_Vulnerability_Research_Team) (VRT)** : Estas son las reglas de Snort “oficiales”. Son proporcionados por Sourcefire y son actualizados semanalmente por Sourcefire VRT.
- **[Emerging Threats](https://ciberseguridad.blog/reglas-snort-deteccion-de-intrusos-y-uso-no-autorizado/Emerging%20Threats%20(ET)) (ET)** : Las reglas de amenazas emergentes son un proyecto comunitario de código abierto. Este conjunto es el conjunto de reglas de Snort más diverso y de movimiento más rápido. Las reglas se actualizan varias veces al día.
- **[Reglas de la comunidad](https://www.snort.org/downloads/#rule-downloads)** : Estas reglas son creadas por la comunidad de SNORT. Hay muy pocas reglas y la última versión es de 2007 para Snort 2.4. La mayoría de las amenazas que detectan ya están implementadas en ET o VRT.
- **Reglas caseras y otras** : Son las reglas, creadas y mantenidas localmente, según las necesidades específicas de la red. También pueden existir otras reglas. Para amenazas específicas y otras amenazas “únicas”, los motores de búsqueda pueden proporcionar reglas más específicas, pero es necesario saber qué buscar.

# Formato de reglas en snort
![formato](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/6d62dfb7b6c9ffbe46b200fea020154dfdcadd28/creacion%20de%20reglas%20para%20snort/Img-rules/1.PNG)

# opciones de deteccion
![deteccion](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/6d62dfb7b6c9ffbe46b200fea020154dfdcadd28/creacion%20de%20reglas%20para%20snort/Img-rules/2.PNG)

# Analisis de reglas
![analisis](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/ea733338b12c04b1b5b69b0c7882fed67b6e7d61/creacion%20de%20reglas%20para%20snort/Img-rules/4.PNG)

## Las diferentes opciones que nos podemos encotrar en la cabecera son las siguientes:
# Acción

- Alert: se envia una alerta y guarda la informacion en el archivo de log
- log: la regla se dispara pero solamente se guarda en el archivo de log
- pass: ignora el paquete
- drop: si la regla se dispara se bloquea el paquete y se guarda la informacion en el log
- reject: se bloquea el paquete y se fuerza el fallo de la comunicacion
- sdrop: se bloquea el paquete pero no se deja constacia del log

# Origen y destino
- se pueden usar tanto como origen como destino una red o una ip, además de poder usar las variables definidas en el archivo de reconfiguracion.
- any: significa que es valido cualquier IP o red

# Dirección
- ->: la regla solo actúa en una dirección Origen hacia Destino.
- <>: La regla actúa en ambas direcciones.

## Ejemplo 1:
```
alert tcp $HOME_NET 21 -> any any (msg: "Error autentificacion FTP"; contet:"login or password incorrect"; sid:1000003; rev:1;)
```
- Accion: alert
- protocolo: TCP
- Origen: $HOME_NET
- puerto de Origen: 21
- Destino: Cualquiera
- Puerto Destino:cualquiera
- Direccion: solamente hacia destino
## Ejemplo 2:
```
alert tcp $EXTERNAL_NET any -> $HOME_NET 3306 (msg: "MYSQL show databases attempt"; flow:to_server,established; content:"|0F 00 00 00 03| show databases") 
```
- Acción: Alert 
- Protocolo: TCP
- Origen: $EXTERNAL_NET
- Puerto: Cualquiera
- Direccion: solamente hacia el destino
- Destino: cualquiera
- Puerto Destino: 3306 

### Ejemplo de la implementacion de reglas de snort en ubuntu
```
alert icmp 192.168.0.1/24 any -> any any (msg:"alguien esta haciendo ping";sid:19910316;rev:1;)
```
![ejemplo](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/1e6ee29202666b1d30efcdd0051cf51d401163c9/creacion%20de%20reglas%20para%20snort/Img-rules/12.PNG)

## Snort implementando la regla que creamos
![snort](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/1e6ee29202666b1d30efcdd0051cf51d401163c9/instalacion%20de%20snort%20en%20ubuntu/snort-img/haciendo%20ping%20a%20la%20maquina.PNG)
