---
title: 'Lync Server 2013: llamadas entrantes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05147e469ce120663992e5ae7b8a3ee59acaf78c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526617"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="afea2-102">Llamadas entrantes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afea2-102">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afea2-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="afea2-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="afea2-104">El enrutamiento de llamadas entrantes a los usuarios habilitados para Location-Based el enrutamiento depende de la ubicación del extremo del usuario.</span><span class="sxs-lookup"><span data-stu-id="afea2-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="afea2-105">El enrutamiento de las llamadas entrantes se ve afectado de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="afea2-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="afea2-106">Si un usuario tiene una llamada entrante a un punto de conexión que se encuentra en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en el mismo sitio de red que la puerta de enlace RTC, la llamada se redirigirá.</span><span class="sxs-lookup"><span data-stu-id="afea2-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="afea2-107">Si un usuario tiene una llamada entrante a un punto de conexión que se encuentra en un sitio de red habilitado para enrutamiento de Location-Based y el extremo se encuentra en un sitio de red diferente de la puerta de enlace RTC, no se enrutará la llamada.</span><span class="sxs-lookup"><span data-stu-id="afea2-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="afea2-108">Cuando un usuario no tiene extremos ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se redirigirá directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la persona que ha recibido la llamada.</span><span class="sxs-lookup"><span data-stu-id="afea2-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="afea2-109">La configuración de desvío de llamadas de un usuario que está habilitada para Location-Based el enrutamiento seguirá aplicándose, pero las llamadas reenviadas estarán sujetas a Location-Based restricciones de enrutamiento del usuario.</span><span class="sxs-lookup"><span data-stu-id="afea2-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="afea2-110">En la tabla siguiente se muestra cómo el enrutamiento de Location-Based afecta al enrutamiento de las llamadas entrantes en función de la ubicación del extremo del destinatario de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afea2-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="afea2-111">El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento Location-Based y Location-Based enrutamiento solo permite el enrutamiento de llamadas RTC a extremos dentro del mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="afea2-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="afea2-112">Destinatario de la llamada que recibe una llamada entrante de la RTC</span><span class="sxs-lookup"><span data-stu-id="afea2-112">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="afea2-113">Extremo del destinatario de la llamada que se encuentra en el mismo sitio de red que la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="afea2-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="afea2-114">Extremo del destinatario de la llamada no ubicado en el mismo sitio de red que la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="afea2-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="afea2-115">Extremo del destinatario de la llamada ubicado en un sitio de red desconocido o no habilitado para el enrutamiento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="afea2-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afea2-116">Enrutamiento de llamadas RTC entrantes</span><span class="sxs-lookup"><span data-stu-id="afea2-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="afea2-117">La llamada entrante se redirige a los extremos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="afea2-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="afea2-118">La llamada entrante no se enruta a los extremos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="afea2-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="afea2-119">La llamada entrante no se enruta a los extremos del destinatario de la llamada</span><span class="sxs-lookup"><span data-stu-id="afea2-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="afea2-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afea2-120">See Also</span></span>


[<span data-ttu-id="afea2-121">Escenarios para Location-Based el enrutamiento en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afea2-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

