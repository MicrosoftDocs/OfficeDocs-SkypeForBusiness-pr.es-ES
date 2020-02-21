---
title: 'Lync Server 2013: información general sobre la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66c2484b656cce15a6f7d013060c1fc95047f49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Información general sobre la omisión de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

El desvío de medios es útil para minimizar la cantidad de servidores de mediación implementados. En general, un grupo de servidores de mediación se implementa en un sitio central y controla puertas de enlace en los sitios de sucursal. Habilitar el desvío de medios permite que las llamadas de red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Lync Server 2013 las rutas de llamadas salientes y las directivas de Enterprise Voice deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.

Las redes Wi-Fi suelen tener más pérdidas de paquetes que las redes por cable. En general, las puertas de enlace no pueden asumir la recuperación de la pérdida de paquetes. Por lo tanto, antes de decidir si debe habilitarse el desvío de medios para una subred inalámbrica, se recomienda evaluar la calidad de una red Wi-Fi. La reducción de latencia presenta unas contrapartidas respecto a la recuperación de pérdida de paquetes que también deben tenerse en cuenta. RTAudio, un códec disponible para llamadas que no desvían el servidor de mediación, es más apropiado para ocuparse de la pérdida de paquetes.

Una vez que se haya implementado la estructura de Enterprise Voice, la planeación de la omisión de medios es sencilla.

  - Si tiene una topología centralizada sin vínculos WAN a redes de sucursal, puede habilitar un desvío de medios global porque no se necesita control ajustado.

  - Si tiene una topología distribuida compuesta de una o más regiones de red y sus sitios de sucursal afiliados, determine los aspectos siguientes:
    
      - Si los homólogos del servidor de mediación pueden asumir las capacidades que se requieren para el desvío de medios.
    
      - Los sitios de cada región de redes que están bien conectados.
    
      - La combinación de desvío de medios y control de admisión de llamadas que es apropiada para la red.

Al habilitar el desvío de medios, se genera automáticamente un identificador de desvío único para una región de red y para todos los sitios de red que no tengan restricciones de ancho de banda en dicha región. A los sitios con restricciones de ancho de banda dentro de la región y a los sitios conectados a la región mediante vínculos WAN con restricciones de ancho de banda se les asignan sus propios identificadores de desvío únicos.

Cuando un usuario realiza una llamada a la RTC, el servidor de mediación compara el identificador de omisión de la subred del cliente con el identificador de omisión de la subred de la puerta de enlace. Si los dos identificadores de desvío coinciden, se usará el desvío de medios para la llamada. Si los identificadores de omisión no coinciden, los medios de la llamada deben fluir a través del servidor de mediación.

Cuando un usuario recibe una llamada de la RTC, el cliente del usuario compara su identificador de desvío con el de la puerta de enlace RTC. Si los dos identificadores de omisión coinciden, los medios se transmiten directamente de la puerta de enlace al cliente, omitiendo el servidor de mediación.

Solo los clientes y dispositivos de Lync 2010 o posterior admiten interacciones de omisión de medios con un servidor de mediación.

<div>


> [!IMPORTANT]  
> Además de habilitar el desvío de medios de manera global, debe habilitarse en cada tronco RTC. Si el desvío se habilita globalmente pero no se habilita en un determinado tronco RTC, no se invocará el desvío de medios en ninguna de las llamadas en las que intervenga ese tronco RTC. Asimismo, si el desvío de medios se define en <STRONG>Usar información de región y sitio</STRONG>, todas las subredes enrutables deben asociarse con los sitios en los que se ubican. Si en un sitio hay subredes enrutables en las que no se desea habilitar el desvío, dichas subredes deben agruparse en un sitio nuevo antes de habilitar el desvío de medios. Esta acción asegurará que las subredes no enrutables tengan asignado un identificador de desvío diferente.



</div>

<div>

## <a name="see-also"></a>Consulta también


[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

