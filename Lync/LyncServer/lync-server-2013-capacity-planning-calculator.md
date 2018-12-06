---
title: Usar la calculadora de planeamiento de capacidad de Lync Server 2013
TOCTitle: Usar la calculadora de planeamiento de capacidad de Lync Server 2013
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56271367
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Usar la calculadora de planeamiento de capacidad de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La calculadora de planeamiento de capacidad de Microsoft® Lync™ Server 2013 se puede descargar en <http://www.microsoft.com/en-us/download/details.aspx?id=36828>. Se ha diseñado para ayudarle a determinar los requisitos de servidor en función de las modalidades de comunicación y los usuarios que haya habilitado en la organización. Especifique el perfil de la organización y la calculadora le facilitará recomendaciones para planear la topología.

La calculadora solo crea recomendaciones a efectos de planeación. Se requiere la simulación de carga real para garantizar el aprovisionamiento correcto de Lync Server 2013. Para realizar la prueba de esfuerzo con una carga simulada, use la [Herramienta de esfuerzo y de rendimiento de Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).

Tras determinar el perfil de usuario y las modalidades que desea habilitar para los usuarios, es el momento de usar la calculadora para planear las necesidades de número de servidores, memoria y ancho de banda. Esta versión de la calculadora no ofrece instrucciones sobre los requisitos de E/S de disco.

Esta calculadora complementa a [Microsoft Lync Server](http://go.microsoft.com/fwlink/?linkid=282725) y [Microsoft Lync Server](lync-server-2013-planning.md). Antes de usarla, consulte la guía y cree una de las topologías recomendadas con la Herramienta de planeación.

Para sacar el máximo partido de la calculadora necesitará información precisa y detallada sobre el perfil de usuario específico. Por ejemplo, datos como el porcentaje de usuarios habilitados para voz, la media de llamadas por usuario por hora, la duración de las llamadas y el porcentaje de usuarios simultáneos en las conferencias pueden suponer una gran diferencia en cuanto a requisitos de servidor. La precisión de las recomendaciones de la calculadora dependerá de la precisión de la información que se le suministre.

## Uso de la calculadora de capacidad

La calculadora es una hoja de cálculo de Microsoft Excel®. Usted debe escribir la información en las celdas de color naranja. Aunque aparecen los valores predeterminados (80.000 usuarios en un grupo con doce servidores front-end), puede cambiarlos en función de las necesidades de la organización.

El modelo de uso contiene las secciones siguientes. Para calcular los requisitos de capacidad, escriba los datos según se especifica:

**Mensajería instantánea y presencia**

  - Bajo Número de usuarios, escriba el número de usuarios que mantendrán una sesión abierta de forma simultánea. Por lo general, este número asciende al 80 % del número total de usuarios especificado. En muchas ocasiones, el 100% de los usuarios simultáneos estarán habilitados para mensajería instantánea y presencia. El valor predeterminado es 80.000.

  - El número medio de contactos de la Lista de contactos es el número de contactos que deberá usar para validar los requisitos del sistema. Este número no puede modificarse.

**Telefonía IP empresarial**

  - En Usuarios habilitados para Telefonía IP empresarial, escriba el porcentaje de los usuarios que se han habilitado para este tipo de telefonía. El valor predeterminado es el 60 %.

  - En Número medio de llamadas por usuario por hora (pico), escriba el número de llamadas por hora en las que calcula que participará el usuario medio durante las horas de pico de carga. El valor predeterminado es 4.

  - En Porcentaje de llamadas con omisión de medios, escriba el porcentaje de llamadas de los usuarios que omitirán el servidor de mediación. El valor predeterminado es el 65 %.

  - En Porcentaje de usuarios de voz en llamadas de UC a RTC, escriba el porcentaje de llamadas de la organización que son llamadas telefónicas de UC a RTC. El valor predeterminado es el 60 %.

  - Porcentaje de usuarios de voz en llamadas de UC a UC muestra el porcentaje de usuarios habilitados para Telefonía IP empresarial que solo podrán realizar llamadas de UC a UC. Este número se calcula en función del dato que se ha especificado en Porcentaje de usuarios de voz en llamadas de UC a RTC.

**Conferencia**

  - En Porcentaje de usuarios en conferencias simultáneas, escriba el porcentaje de usuarios que participarán en conferencias de forma simultánea. El valor predeterminado es el 5 %.

  - En Porcentaje de conferencias solo con sesión de mensajería instantánea en grupo (sin voz), escriba el porcentaje de conferencias en las que solo se usará mensajería instantánea (sin incluir componentes de audio). El valor predeterminado es el 10 %.

  - En Porcentaje de usuarios con conferencia de acceso telefónico local, escriba el porcentaje de participantes simultáneos en conferencias que usarán este tipo de conferencia. El valor predeterminado es el 15 %.

  - En Porcentaje de conferencias con voz, escriba el porcentaje de conferencias que incluirán componentes de audio.
    
      - Si el 20 % de las conferencias de voz incluirán también vídeos comunes, active la casilla Incluye vídeo (sin vista múltiple).
    
      - Si el 20 % de las conferencias incluirán también vídeos en vista múltiple, active la casilla Incluye vista múltiple).
    
      - Si el 50 % de las conferencias de voz incluirán también el uso compartido de aplicaciones, active la casilla Incluye uso compartido de aplicaciones.
    
      - Si el 20 % de las conferencias de voz incluirán también cargas de datos (como las presentaciones de Microsoft PowerPoint®), active la casilla Incluye conferencia web.

**Movilidad**

  - En Porcentaje de usuarios habilitados para movilidad, escriba el porcentaje de usuarios a los que se permitirá conectar con Lync Server a través de dispositivos móviles. El valor predeterminado es el 40 %.

Cuando se especifique toda la información necesaria, la calculadora de capacidad calculará los requisitos. Las celdas amarillas muestran los valores que se han calculado para los requisitos de CPU, memoria y ancho de banda a partir de las pruebas desarrolladas en los laboratorios de rendimiento de Lync Server 2013. Las cifras se ofrecen a título orientativo (no se han comprobado y validado todas las variaciones individuales posibles). Se han calculado los valores siguientes:

  - CPU front-end: porcentaje de uso de la CPU cuando toda la carga se controla desde un servidor front-end con las mismas especificaciones que el servidor que se ha usado en la prueba de Microsoft.

  - Red en Mbps: requisitos de ancho de banda en megabits por segundo (Mbps) para la carga de trabajo correspondiente.

  - Memoria en GB: memoria necesaria en gigabytes (GB) para la carga de trabajo correspondiente.

Las celdas verdes contienen recomendaciones para el modelo de uso que se ha especificado.

  - Número total de servidores front-end: número de servidores físicos necesarios basados en servidores dedicados que ejecutan Lync Server 2013 con procesador dual, 6 núcleos y 2.260 megaciclos.

  - Tenga en cuenta que se recomienda habilitar el hyperthreading ya que se ha demostrado que mejora el rendimiento de los servidores compatibles con audio o vídeo.

  - Servidores perimetrales: número de servidores perimetrales necesarios calculado a partir del 30 % de todos los usuarios simultáneos que usan estos servidores para comunicarse. Este porcentaje de la calculadora no se puede modificar.

  - Almacén de los servicios de archivado/registro detallado de llamadas/calidad de la experiencia: número de almacenes necesarios para las características de archivado o supervisión (si se han habilitado en la organización).

  - Servidores de base de datos back-end necesarios (grupos necesarios): número de servidores de base de datos back-end necesarios para la carga de trabajo que se ha seleccionado.

En la fila situada junto a Número total de servidores front-end, también se facilita información sobre la carga de los servidores y la red para todas las cargas de trabajo combinadas.

  - Carga media de CPU: uso medio de la CPU por servidor front-end.

  - Red en Mbps: asignación de ancho de banda necesario para el modelo de uso que se ha especificado.

  - Memoria en GB: memoria en gigabytes necesaria para cada servidor front-end.

## Ajustar para sus procesadores

Todas las cifras de uso de CPU de la hoja de cálculo presuponen que todos los servidores cuentan con un procesador dual, 6 núcleos con 2,26 GHz, un mínimo de 32 GB de memoria, 8 unidades de disco duro de 10.000 RPM y 72 GB de espacio libre en disco.

Si los servidores tienen distintos procesadores, puede ajustar las cifras a las de su hardware.

