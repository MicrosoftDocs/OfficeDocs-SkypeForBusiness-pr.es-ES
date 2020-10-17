---
title: 'Lync Server 2013: capacidades no compatibles con el enrutamiento de Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40a7d32c0448abfe3552fdfe657b9c6bec960a08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512867"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Capacidades no compatibles con el enrutamiento de Location-Based en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-12_

El enrutamiento Location-Based no se aplica a los siguientes tipos de interacciones. Location-Based el enrutamiento no se aplica cuando los extremos de Lync interactúan con los extremos RTC mediante estas funciones.

  - Acceso telefónico a conferencias RTC

  - Llamadas RTC entrantes y salientes a través del grupo de respuesta

  - Estacionamiento de llamadas o recuperación de llamadas RTC a través del estacionamiento de llamadas

  - Llamadas RTC entrantes al servicio de anuncios

  - Llamadas RTC entrantes recuperadas a través de la atención de llamadas grupales

Para aplicar Location-Based reglas de enrutamiento a los tipos de interacciones de la lista siguiente, debe habilitar el enrutamiento de Location-Based para las conferencias:

  - Acceso telefónico PSTN desde conferencias

  - Escalaciones de conversaciones de audio punto a punto a conferencias en las que intervienen extremos RTC

  - Transferencias de consulta que implican extremos de RTC

Para habilitar el enrutamiento de Location-Based para conferencias, consulte [enrutamiento basado en ubicación para conferencias en Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>Consulte también


[Planeación del enrutamiento de Location-Based en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

