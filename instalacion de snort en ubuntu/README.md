Instalacion de Snort en Ubuntu
=================================

**Objetivos**
* Instalar un sistema IPS o IDS para la proteccion de nuestra red
* Implementar reglas para monitorear la actividad de nuestra red

**Requisitos**
* Maquina Ubuntu
* 4gb de ram para la maquina Ubuntu
* 40gb espacio disponible

**Preparacion de la maquina para la instalacion de snort**
* Iniciar vmware y encender la VM de Ubuntu
* Revisar las actualizaciones de Ubuntu y actualizar a la mas reciente
* Acceder como root con el comando sudo su

**Instalacion de Snort y configuracion** 
* Ingresar el siguiente comando como usuario Root
```
apt-get install snort
```
![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/d7e62ffdead4d774f1a70ad7fe463cc53f2d4ae2/proyecto1/instalacion%20de%20snort%20en%20ubuntu/1.PNG)

**dar siguiente y ingresar el nombre de la interfaz de red**

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/fe236c1aa290b8c68b6b88eeab388c80139c4fe1/proyecto1/instalacion%20de%20snort%20en%20ubuntu/7.PNG)

**ingresar la puerta de enlace**

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/fe236c1aa290b8c68b6b88eeab388c80139c4fe1/proyecto1/instalacion%20de%20snort%20en%20ubuntu/3.PNG)

**ir la consola de la maquina fuera de la virtualizacion y ingresar ipconfig para verificar la puerta de enlace de la red**

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/fe236c1aa290b8c68b6b88eeab388c80139c4fe1/proyecto1/instalacion%20de%20snort%20en%20ubuntu/5.PNG)

**ingresar en la consola el siguiente comando**
```
dpkg-reconfigure snort
```
dejar todo como esta pero ingresar el correo

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/5e9b0bbe948f867b342c265c300c6e5314f9b0d3/proyecto1/instalacion%20de%20snort%20en%20ubuntu/9.PNG)

minimo de ocurrencia 1

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/5e9b0bbe948f867b342c265c300c6e5314f9b0d3/proyecto1/instalacion%20de%20snort%20en%20ubuntu/10.PNG)

**reiniciar Snort con el siguiente comando**
```
/etc/init.d/snort restart
```
## el siguiente paso es verificar el servicio de snort con la siguiente linea de comando
```
service snort status
```
## Acceder con el siguiente comando al archivo de configuracion del snort
```
gedit /etc/snort/snort.conf
```
![alt tecxt](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/43b6f75157c3c3ea69c1fe477d252c7d0a85d96f/instalacion%20de%20snort%20en%20ubuntu/snort-img/13.PNG)

# en el apartado de HOME_NET se coloca la puerta de enlace de la maquina y debajo se coloca el ip de la maquina windows 
![alt tecxt](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/43b6f75157c3c3ea69c1fe477d252c7d0a85d96f/instalacion%20de%20snort%20en%20ubuntu/snort-img/14.PNG)

# despues de agregar las reglas que desee se accede a la carpeta de snort con el siguiente comando 
```
cd /etc/snort/
```
# Por ultimo se ejecuta el monitoreo en consola
```
snort -A console -c snort.conf -i (colocar el nombre de su interfaz de red)
```



