---
title: 'Lync Server 2013: Delegación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82be0bdc382440cc8a4307dc0ba981f31c5a9313
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a>Delegación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-09_

Las capacidades de delegación de Lync se ven afectadas por el enrutamiento basado en la ubicación de la siguiente manera:

  - Cuando un delegado habilitado para el enrutamiento basado en la ubicación realiza una llamada en nombre de un administrador, se usa la Directiva de voz del delegado para autorizar la llamada y se usará la Directiva de enrutamiento de voz del sitio del delegado para enrutar la llamada

  - Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas correspondientes para el reenvío de llamadas o para las llamadas simultáneas, tal como se describe en los temas Transferencias y reenvíos de llamadas y Llamadas simultáneas.

  - Cuando un delegado establece un extremo de RTC como destino de las llamadas simultáneas, para una llamada entrante al administrador, la directiva de enrutamiento de voz del sitio asociado al tronco entrante se usará para redirigir la llamada al extremo de RTC del delegado.

  - Para la delegación, recomendamos que el administrador y sus delegados asociados se ubiquen normalmente en el mismo sitio de red.

<div>

## <a name="see-also"></a>Vea también


[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

