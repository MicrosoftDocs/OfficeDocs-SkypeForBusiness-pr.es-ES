---
title: 'Lync Server 2013: consideraciones sobre la interoperabilidad para conferencias de vídeo'
description: 'Lync Server 2013: consideraciones sobre interoperabilidad para la videoconferencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89675954ea4c4f188f50aab8fb2cb49494bcc247
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543936"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Consideraciones sobre interoperabilidad para la Conferencia de vídeo en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

En esta sección se describe la experiencia del usuario durante la fase de coexistencia de la migración, cuando hay interoperabilidad entre clientes heredados y un grupo de servidores de Lync Server 2013 o clientes de Lync Server 2013 y un grupo de servidores heredados.

<div>

## <a name="lync-server-2013-pools"></a>Grupos de servidores 2013 de Lync Server

Los usuarios experimentarán el siguiente comportamiento cuando se use un cliente heredado en un grupo de servidores de Lync Server 2013:

  - Para llamadas de dos participantes, la resolución de vídeo es la misma que en el grupo de servidores heredado.

  - Para conferencias de varios participantes, las características de resolución de vídeo y conferencia de vídeo son las mismas que en el grupo de servidores heredado. La vista de galería y la alta resolución no están disponibles.

</div>

<div>

## <a name="legacy-pools"></a>Grupos de servidores heredados

Los usuarios experimentarán el siguiente comportamiento cuando se use un cliente de Lync Server 2013 en un grupo de servidores heredados:

  - Para llamadas de dos participantes, los clientes de Lync Server 2013 pueden usar nuevas características de la siguiente manera:
    
      - H. 264 está disponible si ambos participantes usan clientes de Lync Server 2013.
    
      - El cliente de Lync Server 2013 usa el valor predeterminado para TotalReceiveVideoBitRateKb, ya que el servidor heredado no envía esta información con aprovisionamiento en banda.

  - Para conferencias de varios participantes, las características de resolución de vídeo y conferencia de vídeo son las mismas que las que tiene un cliente heredado en el grupo de servidores heredado.

<div>


> [!NOTE]  
> Cuando un servidor heredado hospeda un cliente de Lync Server 2013, es posible configurar el ancho de banda de la Conferencia de vídeo para que todos los usuarios del grupo reciban solo vídeo de baja resolución, pero que envíen vídeo de alta resolución. Un ejemplo de esto es cuando MaxVideoRateAllowed se establece en CIF-250K en la configuración multimedia y VideoBitRateKb se establece en 2000 kbps en la directiva de conferencia. El efecto neto en esta situación es que la resolución alta no es posible para usuarios del grupo de servidores.<BR>Debido a que MaxVideoRateAllowed ya no se usa para los clientes de Lync Server 2013, no puede impedir que los clientes de Lync Server 2013 soliciten vídeo de alta resolución. En su lugar, establezca VideoBitRateKb en la directiva de conferencia para todos los usuarios del grupo de servidores al mismo valor que MaxVideoRateAllowed (es decir, CIF se establece en 250 kbps, o VGA se establece en 600 kbps, o HD se establece en 1500 kbps).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

