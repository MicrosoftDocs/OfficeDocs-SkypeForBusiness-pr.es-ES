---
title: 'Lync Server 2013: Tronco M:N'
TOCTitle: Tronco M:N
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48276878
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tronco M:N en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-01_

Lync Server 2013 tiene mayor flexibilidad en la definición de un tronco para redirigir llamadas que las versiones anteriores. Un tronco es una asociación lógica entre un Servidor de mediación y un número de puerto de escucha con una puerta de enlace y un número de puerto de escucha. Esto tiene varias implicaciones: un Servidor de mediación puede tener varios troncos a una misma puerta de enlace; un Servidor de mediación puede tener varios troncos a diferentes puertas de enlace. Y a la inversa, una puerta de enlace puede tener varios troncos a diferentes Servidores de mediación.

Se sigue necesitando crear un tronco raíz cuando se agrega una puerta de enlace a la topología de Lync con el Generador de topologías. El número de puertas de enlace que un Servidor de mediación puede administrar depende de la capacidad de procesamiento del servidor durante las horas de mayor actividad. Si implementa un Servidor de mediación en hardware que supera los requisitos de hardware mínimos para Lync Server 2013, tal como se describe en [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) en la documentación de compatibilidad, el cálculo de cuántas llamadas activas sin desvío que un Servidor de mediación independiente puede administrar es de unas 1000 llamadas. Cuando se implementan en hardware que cumple estas especificaciones, se espera que el Servidor de mediación efectúe una transcodificación, pero siga enrutando llamadas para varias puertas de enlace, aunque estas no admitan el desvío de medios.

Al definir una ruta de llamada, se especifican los troncos asociados con dicha ruta, pero no se especifican los Servidores de mediación que están asociados con la ruta. En su lugar, se usa el Generador de topologías para asociar troncos con Servidores de mediación. En otras palabras, el enrutamiento determina qué tronco debe usarse para una llamada y, posteriormente, se envía la señalización de la llamada al Servidor de mediación asociado con dicho tronco.

El Servidor de mediación se puede implementar como grupo de servidores. Este grupo se puede combinar con un Grupo de servidores front-end o bien implementarse como grupo de servidores independiente. Cuando se combina un Servidor de mediación con un Grupo de servidores front-end, el tamaño del grupo de servidores puede ser, como mucho, de 12 (el límite de tamaño del grupo de registradores). En conjunto, estas nuevas capacidades aumentan la fiabilidad y la flexibilidad de implementación para los Servidores de mediación, pero necesitan capacidades asociadas en las entidades del mismo nivel que se indican a continuación:

  - **Puerta de enlace RTC.** Una puerta de enlace certificada de Lync Server 2013 debe implementar el equilibrio de carga de DNS, que permite a una puerta de enlace RTC certificada actuar como equilibrador de carga para un grupo de Servidores de mediación y, por lo tanto, equilibrar la carga de llamadas en todo el grupo de servidores.

  - **Controlador de borde de sesión.** Para un tronco SIP, la entidad del mismo nivel es un controlador de borde de sesión (SBC) en un proveedor de servicios de telefonía por Internet. En la dirección del Grupo de servidores de mediación al SBC, el SBC puede recibir conexiones de cualquier Servidor de mediación del grupo de servidores. En la dirección del SBC al grupo de servidores, el tráfico puede enviarse a cualquier Servidor de mediación del grupo de servidores. Esto puede conseguirse mediante el equilibrio de carga de DNS, si el SBC y el proveedor de servicios lo permiten. Una opción es facilitar al proveedor de servicios las direcciones IP de todos los Servidores de mediación del grupo de servidores para que el proveedor de servicios las aprovisione en su SBC como un tronco SIP por separado para cada Servidor de mediación. Después, el proveedor de servicios administrará el equilibrio de carga para sus propios servidores. No todos los proveedores de servicios y SBC admiten estas capacidades. Además, es posible que el proveedor de servicios exija costos adicionales. Por lo general, cada tronco SIP al SBC conlleva una cuota mensual.

  - **IP-PBX.** En la dirección del Grupo de servidores de mediación a la finalización del SIP de IP-PBX, el sistema IP-PBX puede recibir conexiones de cualquier Servidor de mediación del grupo de servidores. En la dirección del sistema IP-PBX al grupo de servidores, el tráfico puede enviarse a cualquier Servidor de mediación del grupo de servidores. Como la mayoría de los sistemas IP-PBX no admiten el equilibrio de carga de DNS, recomendamos definir conexiones SIP directas individuales del sistema IP-PBX para cada Servidor de mediación del grupo de servidores. El sistema IP-PBX administrará su propio equilibrio de carga distribuyendo el tráfico en el grupo troncal. Se da por supuesto que el grupo troncal tiene un conjunto coherente de reglas de enrutamiento en el sistema IP-PBX. Para poder decidir si un clúster de Servidor de mediación puede interactuar correctamente con un sistema IP-PBX, determine si el sistema IP-PBX en cuestión admite el concepto de grupo troncal y de qué forma confluye con la arquitectura de redundancia y clústeres del propio sistema IP-PBX.

Un Grupo de servidores de mediación debe tener una visión uniforme de la puerta de enlace del mismo nivel con la que interactúa. Esto significa que todos los miembros del grupo de servidores obtienen acceso a la misma definición de la puerta de enlace de mismo nivel del almacén de configuración y tienen las mismas posibilidades de interactuar con ella para las llamadas salientes. Por lo tanto, no existe ninguna forma de segmentar el grupo de servidores para que algunos Servidores de mediación solo se comuniquen con determinadas puertas de enlace del mismo nivel para las llamadas salientes. Si tal segmentación es necesaria, deberá usar un grupo de Servidores de mediación separado. Por ejemplo, esto sucedería si las puertas de enlace RTC, troncos SIP o sistemas IP-PBX no tuvieran capacidades asociadas para interactuar con un grupo de servidores, tal y como se ha explicado anteriormente en este mismo tema.

Una puerta de enlace RTC, un sistema IP-PBX o un tronco SIP de mismo nivel pueden enrutar a varios Servidores de mediación o troncos. El número de puertas de enlace que puede controlar un determinado grupo de Servidores de mediación depende del número de llamadas que usan el desvío de medios. Si lo usan una gran cantidad de llamadas, un Servidor de mediación del grupo de servidores puede administrar muchas más llamadas, puesto que solo se necesita el procesamiento de la capa de señalización.

