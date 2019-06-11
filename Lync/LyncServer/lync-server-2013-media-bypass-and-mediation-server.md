---
title: 'Lync Server 2013: Omisión de medios y servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Omisión de medios y servidor de mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

La omisión de multimedia es una función de Lync Server que permite a un administrador configurar el enrutamiento de llamadas para que fluya directamente entre el extremo de usuario y la puerta de enlace de red telefónica conmutada (RTC) sin atravesar el servidor de mediación. La omisión de medios mejora la calidad de las llamadas al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y la cantidad de puntos posibles de error. Cuando un sitio remoto sin un servidor de mediación se conecta a un sitio central mediante uno o varios vínculos WAN con ancho de banda restringido, la omisión de medios disminuye el requisito de ancho de banda al permitir que los medios de un cliente de un sitio remoto fluyan directamente a su puerta de enlace local sin en primer lugar, debe transmitirse a través del vínculo WAN a un servidor de mediación del sitio central y viceversa. Esta reducción en el procesamiento de medios también complementa la capacidad del servidor de mediación de controlar varias puertas de enlace.

La omisión de medios y el servicio de control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa la omisión de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.

<div>

## <a name="see-also"></a>Vea también


[Control de admisión de llamadas y servidor de mediación en Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

