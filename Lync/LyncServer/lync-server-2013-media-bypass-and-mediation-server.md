---
title: 'Lync Server 2013: omisión de medios y servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a33ed2c9b3494e9c67e8ac4a658b6aee75ff7649
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Omisión de medios y servidor de mediación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

La omisión de medios es una capacidad de Lync Server que permite a un administrador configurar el enrutamiento de llamadas para que fluya directamente entre el punto de conexión del usuario y la puerta de enlace de la red telefónica conmutada (RTC) sin atravesar el servidor de mediación. La omisión de medios mejora la calidad de las llamadas al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y la cantidad de puntos de error potenciales. Cuando un sitio remoto sin un servidor de mediación está conectado a un sitio central por uno o más vínculos WAN con ancho de banda restringido, la omisión de medios disminuye el requisito de ancho de banda habilitando los medios de un cliente en un sitio remoto para fluir directamente a su puerta de enlace local sin primero tiene que fluir a través del vínculo WAN hacia un servidor de mediación en el sitio central y hacia atrás. Esta reducción en el procesamiento de medios también complementa la capacidad del servidor de mediación para controlar varias puertas de enlace.

El desvío de medios y el control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa desvío de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.

<div>

## <a name="see-also"></a>Vea también


[Control de admisión de llamadas y servidor de mediación en Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

