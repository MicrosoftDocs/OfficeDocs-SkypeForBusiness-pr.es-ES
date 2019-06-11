---
title: 'Lync Server 2013: Modos de omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a08ec3ae6d985c18e20964a857a74ad40bc7668d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>Modos de omisión de medios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Necesitas configurar la omisión de medios de forma global y para cada tronco RTC individual. Al habilitar la omisión de medios globalmente, tienes dos opciones: **Omitir siempre** y **Usar información de sitio y región**.

Como el propio nombre sugiere, **Omitir siempre** significa que se intentará realizar la omisión de todas las llamadas de RTC. **Omitir siempre** se usa en implementaciones en las que no hay necesidad de habilitar el servicio de control de admisión de llamadas ni de especificar información detallada de configuración con respecto a cuándo intentar la omisión de medios. Además, **Omitir siempre** se usa cuando existe plena conectividad entre los clientes y las puertas de enlace RTC. En esta configuración, todas las subredes se asignan únicamente a un solo identificador de omisión, que el sistema calcula.

Con **Usar información de sitio y región**, se usa el identificador de omisión asociado a la configuración del sitio y de la región para tomar la decisión de omisión. Esta configuración proporciona la flexibilidad de configurar la omisión de medios para las topologías más comunes, ya que proporciona un control más preciso cuando se produce la omisión, además de admitir interacciones con el servicio de control de admisión de llamadas (CAC). El sistema intenta facilitarte la tarea asignando automáticamente identificadores de omisión de la manera siguiente.

  - El sistema asigna automáticamente un único identificador de omisión a cada región.

  - Cualquier sitio conectado a una región por un vínculo WAN sin restricciones de ancho de banda hereda el mismo identificador de omisión de la región.

  - A un sitio asociado a la región por un vínculo WAN con un ancho de banda restringido se le asigna un identificador de omisión distinto al de la región.

  - Las subredes asociadas a cada sitio heredan el identificador de omisión del sitio.

<div>

## <a name="see-also"></a>Vea también


[Información general sobre la omisión de elementos multimedia en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Omisión de medios y control de admisión de llamadas en Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

