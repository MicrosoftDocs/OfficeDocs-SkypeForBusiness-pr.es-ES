---
title: 'Lync Server 2013: capacidades no compatibles con el enrutamiento basado en ubicación'
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
ms.openlocfilehash: 99e28778a8bd299d5ead25220f19b27927a63d44
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Capacidades no compatibles con el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-03-12_

El enrutamiento basado en ubicación no se aplica a los siguientes tipos de interacciones. El enrutamiento basado en ubicación no se aplica cuando los puntos de conexión de Lync interactúan con extremos RTC mediante estas funciones.

  - Acceso telefónico a conferencias RTC

  - Llamadas RTC entrantes y salientes a través del grupo de respuesta

  - Estacionamiento de llamadas o recuperación de llamadas RTC a través del estacionamiento de llamadas

  - Llamadas RTC entrantes al servicio de anuncios

  - Llamadas RTC entrantes recuperadas a través de la atención de llamadas grupales

Para aplicar reglas de enrutamiento basadas en la ubicación a los tipos de interacciones de la lista siguiente, debe habilitar el enrutamiento basado en ubicación para las conferencias:

  - Acceso telefónico PSTN desde conferencias

  - Escalaciones de conversaciones de audio punto a punto a conferencias en las que intervienen extremos RTC

  - Transferencias de consulta que implican extremos de RTC

Para habilitar el enrutamiento basado en ubicación para las conferencias, consulte [enrutamiento basado en ubicación para conferencias en Lync Server 2013](lync-server-2013-location-based-routing-for-conferencing.md).

<div>

## <a name="see-also"></a>Vea también


[Planeación del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

