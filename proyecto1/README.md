Implementacion de Snort en Ubuntu
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

** dar siguiente y ingresar el nombre de la interfaz de red **

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/fe236c1aa290b8c68b6b88eeab388c80139c4fe1/proyecto1/instalacion%20de%20snort%20en%20ubuntu/7.PNG)

** ingresar la puerta de enlace **

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/fe236c1aa290b8c68b6b88eeab388c80139c4fe1/proyecto1/instalacion%20de%20snort%20en%20ubuntu/3.PNG)

** ir la consola de la maquina fuera de la virtualizacion y ingresar ipconfig para verificar la puerta de enlace de la red **

![alt text](https://github.com/jhonybustamante/Implementacion-Snort-Ubuntu/blob/fe236c1aa290b8c68b6b88eeab388c80139c4fe1/proyecto1/instalacion%20de%20snort%20en%20ubuntu/5.PNG)


