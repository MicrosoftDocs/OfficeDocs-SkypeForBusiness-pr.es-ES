---
title: 'Lync Server 2013: omisión de medios y control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49de294605372b4b407f0ee16a3fd5661822074f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Omisión de medios y control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El desvío de medios y el control de admisión de llamadas (CAC) funcionan juntos para administrar el control del ancho de banda para los medios de llamada. La omisión de medios facilita el flujo de medios a través de vínculos bien conectados; El CAC administra el tráfico en vínculos con restricciones de ancho de banda. Dado que la omisión de medios y el CAC son mutuamente excluyentes, debe estar atento a uno cuando Planee la otra. Se admiten las siguientes combinaciones:

  - El CAC y el desvío de medios están habilitados. La omisión de medios debe estar configurada para **usar la información de sitio y región**. Esta información de sitio y región es la misma que la usada para CAC.
    
    Si habilita el CAC, no podrá seleccionar **omitir siempre**y viceversa, ya que las dos configuraciones se excluyen mutuamente. Es decir, solo una de las dos se aplicará a una llamada RTC determinada. En primer lugar, se realiza una comprobación para determinar si la omisión de medios se aplica a la llamada. Si es así, no se usará el CAC. Esto tiene sentido, porque si una llamada es apta para la omisión, es por definición usando una conexión donde no se necesita el CAC. Si no se puede aplicar el método bypass a la llamada (es decir, si no coinciden los identificadores de omisión del cliente y la puerta de enlace), se aplicará el CAC a la llamada.

  - CAC no habilitado y desvío de medios configurado para **omitir siempre**.
    
    En esta configuración, las subredes de cliente y de tronco están asignadas a un solo identificador de omisión, calculado por el sistema.

  - CAC no habilitado y el desvío de medios configurado para **usar la información de sitio y región**.
    
    Cuando se habilita **usar información de sitio y región** , la determinación por omisión funciona esencialmente de la misma manera, independientemente de si CAC está habilitado o no. Es decir, para cualquier llamada RTC, la subred del cliente se asigna a un sitio en particular y se extrae el identificador de omisión de esa subred. De forma similar, la subred de la puerta de enlace se asigna a un sitio en particular y se extrae el identificador de omisión de dicha subred. Solo si los dos identificadores de omisión son idénticos, se omitirá la llamada. Si no son idénticos, no se producirá la omisión de medios.
    
    Aunque el CAC está deshabilitado globalmente, es necesario definir la Directiva de ancho de banda para cada sitio y vínculo si desea usar la configuración de sitio y región para controlar la decisión de omisión. El valor real de la restricción de ancho de banda o su modalidad no importa. El objetivo final es hacer que el sistema calcule automáticamente distintos identificadores de omisión para asociarlos con distintas configuraciones regionales que no estén bien conectadas. Definir una restricción de ancho de banda por definición significa que un vínculo no está bien conectado.

  - El CAC está habilitado y la omisión de medios no está habilitada. Esto sólo se aplicará cuando todas las puertas de enlace y las PBX IP no están conectadas correctamente o no cumplen otros requisitos para la omisión de medios. Para obtener más información sobre los requisitos para la omisión de medios, consulte [Technical Requirements for Media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

<div>

## <a name="see-also"></a>Vea también


[Información general sobre la omisión de medios en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

