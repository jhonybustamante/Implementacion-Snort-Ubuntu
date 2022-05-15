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
