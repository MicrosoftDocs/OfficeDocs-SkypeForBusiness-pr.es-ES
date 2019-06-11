---
title: 'Lync Server 2013: consideraciones de interoperabilidad para videoconferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880b2e41a1ea92b3d6da9cd29153695b474e88f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Consideraciones de interoperabilidad para videoconferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

En esta sección se describe la experiencia del usuario durante la fase de coexistencia de la migración, cuando hay interoperabilidad entre clientes heredados y un grupo de servidores de Lync Server 2013 o clientes de Lync Server 2013 y un grupo heredado.

<div>

## <a name="lync-server-2013-pools"></a>Grupos de 2013 de Lync Server

Los usuarios experimentarán el comportamiento siguiente cuando se use un cliente heredado en un grupo de servidores de Lync Server 2013:

  - Para las llamadas de dos participantes, la resolución de video es la misma que la del grupo heredado.

  - Para las conferencias de varias partes, la resolución de video y las características de las videoconferencias son las mismas que en el grupo heredado. La vista de galería y la alta resolución no están disponibles.

</div>

<div>

## <a name="legacy-pools"></a>Grupos heredados

Los usuarios experimentarán el comportamiento siguiente cuando se use un cliente de Lync Server 2013 en una agrupación heredada:

  - Para las llamadas de dos participantes, los clientes de Lync Server 2013 pueden usar las nuevas características de la siguiente manera:
    
      - H. 264 está disponible si ambos participantes usan clientes de Lync Server 2013.
    
      - El cliente de Lync Server 2013 usa el valor predeterminado para TotalReceiveVideoBitRateKb, ya que el servidor heredado no envía esta información con aprovisionamiento en banda.

  - Para las conferencias de varias partes, las características de videoconferencias y la resolución de video son las mismas que experimenta un cliente heredado en el grupo heredado.

<div>


> [!NOTE]  
> Cuando un servidor heredado hospeda un cliente de Lync Server 2013, es posible configurar ancho de banda de videoconferencias para que todos los usuarios del grupo reciban solo vídeo de baja resolución, pero que envíen video de alta resolución. Un ejemplo de ello es cuando MaxVideoRateAllowed se establece en CIF-250K en la configuración de multimedia y VideoBitRateKb se establece en 2000 kbps en la Directiva de conferencia. El efecto neto en esta situación es que no es posible que los usuarios del grupo tengan una alta resolución.<BR>Como MaxVideoRateAllowed ya no se usa para los clientes de Lync Server 2013, no puede impedir que los clientes de Lync Server 2013 soliciten video de alta resolución. En su lugar, establezca VideoBitRateKb en la Directiva de conferencia para todos los usuarios del grupo al mismo valor que MaxVideoRateAllowed (es decir, CIF se establece en 250 kbps o VGA se establece en 600 Kbps, o HD se establece en 1500 kbps).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

