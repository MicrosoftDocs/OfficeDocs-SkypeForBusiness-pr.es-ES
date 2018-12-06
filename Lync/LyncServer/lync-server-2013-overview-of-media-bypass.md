---
title: 'Lync Server 2013: Introducción general a la omisión de medios'
TOCTitle: Introducción general a la omisión de medios
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48276153
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Introducción general a la omisión de medios en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

El desvío de medios es útil para minimizar la cantidad de servidores de mediación implementados. En general, un grupo de servidores de mediación se implementa en un sitio central y controla puertas de enlace en los sitios de sucursal. Habilitar el desvío de medios permite que las llamadas de red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Las directivas de Telefonía IP empresarial y las rutas de llamadas salientes de Lync Server 2013 deben configurarse correctamente para que las llamadas de RTC de clientes en un sitio de sucursal se enruten a la puerta de enlace correspondiente.

Las redes Wi-Fi suelen tener más pérdidas de paquetes que las redes por cable. En general, las puertas de enlace no pueden asumir la recuperación de la pérdida de paquetes. Por lo tanto, antes de decidir si debe habilitarse el desvío de medios para una subred inalámbrica, se recomienda evaluar la calidad de una red Wi-Fi. La reducción de latencia presenta unas contrapartidas respecto a la recuperación de pérdida de paquetes que también deben tenerse en cuenta. RTAudio, un códec disponible para llamadas que no desvían el servidor de mediación, es más apropiado para ocuparse de la pérdida de paquetes.

Una vez configurada la estructura de Telefonía IP empresarial, planear el desvío de medios es un proceso sencillo.

  - Si tiene una topología centralizada sin vínculos WAN a redes de sucursal, puede habilitar un desvío de medios global porque no se necesita control ajustado.

  - Si tiene una topología distribuida compuesta de una o más regiones de red y sus sitios de sucursal afiliados, determine los aspectos siguientes:
    
      - Si los homólogos del servidor de mediación pueden asumir las capacidades que se requieren para el desvío de medios.
    
      - Los sitios de cada región de redes que están bien conectados.
    
      - La combinación de desvío de medios y control de admisión de llamadas que es apropiada para la red.

Al habilitar el desvío de medios, se genera automáticamente un identificador de desvío único para una región de red y para todos los sitios de red que no tengan restricciones de ancho de banda en dicha región. A los sitios con restricciones de ancho de banda dentro de la región y a los sitios conectados a la región mediante vínculos WAN con restricciones de ancho de banda se les asignan sus propios identificadores de desvío únicos.

Cuando un usuario realiza una llamada a la RTC, el Servidor de mediación compara el identificador de desvío de la subred del cliente con el identificador de desvío de la subred de la puerta de enlace. Si los dos identificadores de desvío coinciden, se usará el desvío de medios para la llamada. Si los identificadores de desvío no coinciden, los medios de la llamada deberán transmitirse a través del Servidor de mediación.

Cuando un usuario recibe una llamada de la RTC, el cliente del usuario compara su identificador de desvío con el de la puerta de enlace RTC. Si los dos identificadores de desvío coinciden, los medios se transmitirán directamente de la puerta de enlace al cliente, omitiendo el Servidor de mediación.

Solo los clientes y dispositivos de Lync 2010 o versiones posteriores admiten interacciones de desvío de medios con un Servidor de mediación.

> [!IMPORTANT]  
> Además de habilitar el desvío de medios de manera global, debe habilitarse en cada tronco RTC. Si el desvío se habilita globalmente pero no se habilita en un determinado tronco RTC, no se invocará el desvío de medios en ninguna de las llamadas en las que intervenga ese tronco RTC. Asimismo, si el desvío de medios se define en <strong>Usar información de región y sitio</strong> , todas las subredes enrutables deben asociarse con los sitios en los que se ubican. Si en un sitio hay subredes enrutables en las que no se desea habilitar el desvío, dichas subredes deben agruparse en un sitio nuevo antes de habilitar el desvío de medios. Esta acción asegurará que las subredes no enrutables tengan asignado un identificador de desvío diferente.



## Vea también

#### Conceptos

[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

