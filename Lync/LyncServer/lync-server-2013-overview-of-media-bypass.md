---
title: 'Lync Server 2013: información general sobre la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a>Información general sobre la omisión de elementos multimedia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

La omisión de elementos multimedia es útil cuando desea minimizar el número de servidores de mediación implementados. Normalmente, un grupo de servidores de mediación se implementará en un sitio central y controlará las puertas de enlace en los sitios de sucursales. Habilitar la omisión de medios permite que las llamadas de la red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios. Las directivas de llamadas salientes de Lync Server 2013 y de Enterprise Voice deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.

Las redes Wi-Fi suelen tener más pérdidas de paquetes que las redes por cable. En general, las puertas de enlace no pueden asumir la recuperación de la pérdida de paquetes. Por lo tanto, antes de decidir si necesitas habilitar la omisión de medios para una subred inalámbrica, te recomendamos evaluar la calidad de una red Wi-Fi. La reducción de latencia presenta una contrapartida respecto a la recuperación de la pérdida de paquetes que también necesitas tener en cuenta. RTAudio, un códec disponible para llamadas que no omiten el servidor de mediación, es más apropiado para la gestión de la pérdida de paquetes.

Una vez que la estructura de telefonía empresarial está en vigor, la planeación de la omisión de elementos multimedia es sencilla.

  - Si tienes una topología centralizada sin vínculos WAN a sitios de sucursal, puedes habilitar la omisión de medios global porque no se necesita control de ajustes.

  - Si tienes una topología distribuida compuesta de una o más regiones de red y sus sitios de sucursal afiliados, determina los aspectos siguientes:
    
      - Si los componentes del mismo nivel del servidor de mediación pueden asumir las capacidades que se requieren para la omisión de medios.
    
      - Los sitios de cada región de red que están bien conectados.
    
      - La combinación de la omisión de medios y el servicio de control de admisión de llamadas que es apropiada para la red.

Al habilitar la omisión de medios, se genera automáticamente un identificador de omisión único para una región de red y para todos los sitios de red que no tengan restricciones de ancho de banda en dicha región. A los sitios con restricciones de ancho de banda dentro de la región y a los sitios conectados a la región a través de vínculos WAN con restricciones de ancho de banda se les asignan sus propios identificadores de omisión únicos.

Cuando un usuario realiza una llamada a la RTC, el servidor de mediación compara el identificador de omisión de la subred del cliente con el identificador de omisión de la subred de la puerta de enlace. Si los dos identificadores de omisión coinciden, se usará la omisión de medios para la llamada. Si los identificadores de omisión no coinciden, el medio para la llamada debe fluir por el servidor de mediación.

Cuando un usuario recibe una llamada de la RTC, el cliente del usuario compara su identificador de omisión con el de la puerta de enlace RTC. Si los dos identificadores de omisión coinciden, los medios fluyen directamente de la puerta de enlace al cliente, omitiendo el servidor de mediación.

Solo los clientes y dispositivos de Lync 2010 o superior admiten interacciones de omisión de contenido multimedia con un servidor de mediación.

<div>


> [!IMPORTANT]  
> Además de habilitar la omisión de medios de manera global, necesitas habilitar la omisión de medios en cada tronco RTC de forma individual. Si la omisión se habilita globalmente, pero no se habilita en un determinado tronco RTC, no se invocará la omisión de medios en ninguna de las llamadas en las que intervenga ese tronco RTC. Asimismo, si la omisión de medios se define en <STRONG>Usar información de región y sitio</STRONG>, todas las subredes que se pueden redirigir necesitan asociarse con los sitios en los que se ubican. Si en un sitio hay subredes que se pueden redirigir en las que no se desea habilitar la omisión, dichas subredes necesitan agruparse en un sitio nuevo antes de habilitar la omisión de medios. Esta acción asegurará que las subredes que no se pueden redirigir tengan asignado un identificador de omisión diferente.



</div>

<div>

## <a name="see-also"></a>Vea también


[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

