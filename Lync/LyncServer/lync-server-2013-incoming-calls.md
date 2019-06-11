---
title: 'Lync Server 2013: Llamadas entrantes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c007fbaec317a8e9d9d374ea62dafcab6c7a63f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="b53f9-102">Llamadas entrantes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b53f9-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b53f9-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="b53f9-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="b53f9-104">El enrutamiento de llamadas entrantes a los usuarios habilitados para el enrutamiento basado en la ubicación depende de la ubicación del extremo del usuario.</span><span class="sxs-lookup"><span data-stu-id="b53f9-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="b53f9-105">El enrutamiento de llamadas entrantes se ve afectado de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="b53f9-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="b53f9-106">Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento basado en ubicación y el punto final se encuentra en el mismo sitio de red que la puerta de enlace PSTN, la llamada se redirigirá.</span><span class="sxs-lookup"><span data-stu-id="b53f9-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="b53f9-107">Si un usuario tiene una llamada entrante a un extremo ubicado en un sitio de red habilitado para enrutamiento basado en ubicación y el punto final se encuentra en un sitio de red diferente de la puerta de enlace PSTN, la llamada no se redirigirá.</span><span class="sxs-lookup"><span data-stu-id="b53f9-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="b53f9-108">Cuando un usuario no tenga extremos ubicados en el mismo sitio de red que la puerta de enlace RTC desde la que se origina la llamada entrante, la llamada entrante se redirigirá directamente al correo de voz del usuario y se enviará una notificación de llamada perdida a la persona a la que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="b53f9-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="b53f9-109">La configuración del desvío de llamadas de un usuario habilitado para el enrutamiento basado en la ubicación se seguirá aplicando; sin embargo, las llamadas desviadas estarán sujetas a las restricciones de enrutamiento basadas en la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="b53f9-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="b53f9-110">En la tabla siguiente se muestra cómo afecta el enrutamiento basado en la ubicación al enrutamiento de las llamadas entrantes en función de la ubicación del punto final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b53f9-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="b53f9-111">El sitio de red de la puerta de enlace RTC está habilitado para el enrutamiento basado en la ubicación y el enrutamiento basado en la ubicación solo permite el enrutamiento de llamadas RTC a puntos de conexión dentro del mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="b53f9-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="b53f9-112">El destinatario recibe una llamada entrante desde la RTC</span><span class="sxs-lookup"><span data-stu-id="b53f9-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="b53f9-113">El extremo del destinatario se encuentra en el mismo sitio de red que la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="b53f9-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="b53f9-114">El extremo del destinatario no se encuentra en el mismo sitio de red que la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="b53f9-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="b53f9-115">El extremo del destinatario se encuentra en un sitio de red desconocido o no habilitado para el enrutamiento basado en ubicación</span><span class="sxs-lookup"><span data-stu-id="b53f9-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b53f9-116">Enrutamiento de una llamada RTC entrante</span><span class="sxs-lookup"><span data-stu-id="b53f9-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="b53f9-117">La llamada entrante se redirige a los extremos del destinatario</span><span class="sxs-lookup"><span data-stu-id="b53f9-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="b53f9-118">La llamada entrante no se redirige a los extremos del destinatario</span><span class="sxs-lookup"><span data-stu-id="b53f9-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="b53f9-119">La llamada entrante no se redirige a los extremos del destinatario</span><span class="sxs-lookup"><span data-stu-id="b53f9-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="b53f9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b53f9-120">See Also</span></span>


[<span data-ttu-id="b53f9-121">Escenarios para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b53f9-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

