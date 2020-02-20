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
ms.openlocfilehash: 360223733f003c30d63ef0145fa04c51503d510d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="4fe26-102">Delegación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe26-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fe26-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4fe26-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4fe26-104">Las funciones de delegación de Lync se ven afectadas por el enrutamiento basado en ubicación de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4fe26-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="4fe26-105">Cuando un delegado habilitado para el enrutamiento basado en ubicación realiza una llamada en nombre de un administrador, se usa la Directiva de voz del delegado para autorizar la llamada y se usará la Directiva de enrutamiento de voz del sitio del delegado para enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="4fe26-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="4fe26-106">Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas aplicables a las llamadas de desvío de llamadas o de llamadas simultáneas, tal y como se describe en los temas de transferencia y reenvío y llamada simultánea.</span><span class="sxs-lookup"><span data-stu-id="4fe26-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="4fe26-107">Cuando un delegado establece un punto final de RTC como destino de llamada simultánea, para una llamada entrante al administrador, se usará la Directiva de enrutamiento de voz del sitio asociado al tronco entrante para enrutar la llamada al punto de conexión RTC del delegado.</span><span class="sxs-lookup"><span data-stu-id="4fe26-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="4fe26-108">Para la delegación, se recomienda que el administrador y sus delegados asociados se encuentren normalmente en el mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="4fe26-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4fe26-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fe26-109">See Also</span></span>


[<span data-ttu-id="4fe26-110">Escenarios para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fe26-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

