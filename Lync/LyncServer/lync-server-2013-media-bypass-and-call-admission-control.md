---
title: 'Lync Server 2013: Omisión de medios y control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Omisión de medios y control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El servicio de control de admisión de llamadas (CAC) y la omisión de medios funcionan conjuntamente para administrar el control del ancho de banda para medios telefónicos. La omisión de medios facilita el flujo de medios a través de vínculos con buenas conexiones; el CAC administra el tráfico en vínculos con restricciones de ancho de banda. Como la omisión de medios y el CAC son mutuamente exclusivos, deberás tener en cuenta a cada uno de ellos al realizar la planificación del otro. Se admiten las siguientes combinaciones:

  - Tanto el CAC como la omisión de medios están habilitados. La omisión de medios necesita estar configurada con **Usar información de sitio y región**. La información de sitio y región es la misma que la usada para el CAC.
    
    Si habilitas el CAC, no podrás seleccionar **Omitir siempre**, y viceversa, ya que las dos configuraciones son mutuamente exclusivas; es decir, solo se aplicará una de las dos a una llamada RTC determinada. En primer lugar, se realiza una comprobación para determinar si se aplica la omisión de medios a la llamada. Si es así, no se usa el CAC. Es lógico, ya que si una llamada reúne las condiciones necesarias para la omisión, está usando, por definición, una conexión que no requiere el servicio de control de admisión de llamadas. Si no puede aplicarse la omisión a la llamada (es decir, si los identificadores de omisión del cliente y de la puerta de enlace no coinciden), se aplicará el CAC a la llamada.

  - CAC no habilitado y la omisión de medios configurada con **Omitir siempre**.
    
    En esta configuración, las subredes tanto del tronco como del cliente están asignadas a un solo identificador de omisión, y el sistema lo calcula.

  - CAC no habilitado y la omisión de medios configurada con **Usar información de sitio y región**.
    
    Cuando **Usar información de sitio y región** está habilitado, la determinación de omisión funciona básicamente del mismo modo, independientemente de si el CAC está habilitado o no. Es decir, para todas las llamadas RTC, la subred del cliente está asignada a un sitio en particular, y se extrae el identificador de omisión para dicha subred. Del mismo modo, la subred de la puerta de enlace está asignada a un sitio en particular, y se extrae el identificador de omisión para dicha subred. La omisión de la llamada solo se producirá si los dos identificadores de omisión son idénticos. Si no es así, la omisión de medios no tendrá lugar.
    
    Incluso aunque el CAC esté deshabilitado globalmente, es necesario definir la directiva de ancho de banda para cada uno de los sitios y vínculos si deseas usar una configuración de sitio y región para controlar la decisión de omisión. El valor real de la restricción de ancho de banda o su modalidad no es relevante. El objetivo final es hacer que el sistema calcule automáticamente diferentes identificadores de omisión para asociarse con diferentes configuraciones regionales que no tienen una buena conexión. La definición de una restricción de ancho de banda significa por definición que un vínculo no tiene una buena conexión.

  - El CAC está habilitado y la omisión de medios no está habilitada. Esto se aplica únicamente cuando todas las puertas de enlace y las IP-PBX presentan una conexión deficiente o no reúnen otros requisitos para la omisión de medios. Para obtener más información sobre los requisitos para la omisión de multimedia, consulte [requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

<div>

## <a name="see-also"></a>Vea también


[Información general sobre la omisión de elementos multimedia en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

