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
ms.openlocfilehash: 8da9568ae4cd613dcba0760fb4a8b20295fbb68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="cca5f-102">Delegación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cca5f-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cca5f-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="cca5f-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="cca5f-104">Las capacidades de delegación de Lync se ven afectadas por el enrutamiento basado en la ubicación de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="cca5f-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="cca5f-105">Cuando un delegado habilitado para el enrutamiento basado en la ubicación realiza una llamada en nombre de un administrador, se usa la Directiva de voz del delegado para autorizar la llamada y se usará la Directiva de enrutamiento de voz del sitio del delegado para enrutar la llamada</span><span class="sxs-lookup"><span data-stu-id="cca5f-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="cca5f-106">Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas correspondientes para el reenvío de llamadas o para las llamadas simultáneas, tal como se describe en los temas Transferencias y reenvíos de llamadas y Llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="cca5f-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="cca5f-107">Cuando un delegado establece un extremo de RTC como destino de las llamadas simultáneas, para una llamada entrante al administrador, la directiva de enrutamiento de voz del sitio asociado al tronco entrante se usará para redirigir la llamada al extremo de RTC del delegado.</span><span class="sxs-lookup"><span data-stu-id="cca5f-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="cca5f-108">Para la delegación, recomendamos que el administrador y sus delegados asociados se ubiquen normalmente en el mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="cca5f-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="cca5f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca5f-109">See Also</span></span>


[<span data-ttu-id="cca5f-110">Escenarios para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cca5f-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

