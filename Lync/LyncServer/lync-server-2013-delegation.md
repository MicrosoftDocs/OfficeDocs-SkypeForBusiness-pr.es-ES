---
title: 'Lync Server 2013: Delegación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57de37ff1ef0b43a8a6ea9c03b715d3ebe570a6b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Delegación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Las funciones de delegación de Lync se ven afectadas por el enrutamiento basado en ubicación de la siguiente manera:

  - Cuando un delegado habilitado para el enrutamiento basado en ubicación realiza una llamada en nombre de un administrador, se usa la Directiva de voz del delegado para autorizar la llamada y se usará la Directiva de enrutamiento de voz del sitio del delegado para enrutar la llamada.

  - Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas aplicables a las llamadas de desvío de llamadas o de llamadas simultáneas, tal y como se describe en los temas de transferencia y reenvío y llamada simultánea.

  - Cuando un delegado establece un punto final de RTC como destino de llamada simultánea, para una llamada entrante al administrador, se usará la Directiva de enrutamiento de voz del sitio asociado al tronco entrante para enrutar la llamada al punto de conexión RTC del delegado.

  - Para la delegación, se recomienda que el administrador y sus delegados asociados se encuentren normalmente en el mismo sitio de red.

<div>

## <a name="see-also"></a>Consulta también


[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

