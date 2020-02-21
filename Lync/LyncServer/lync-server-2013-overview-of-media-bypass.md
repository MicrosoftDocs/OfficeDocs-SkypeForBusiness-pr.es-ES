---
title: 'Lync Server 2013: información general sobre la omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66c2484b656cce15a6f7d013060c1fc95047f49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="3dd28-102">Información general sobre la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dd28-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dd28-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3dd28-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3dd28-104">El desvío de medios es útil para minimizar la cantidad de servidores de mediación implementados.</span><span class="sxs-lookup"><span data-stu-id="3dd28-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="3dd28-105">En general, un grupo de servidores de mediación se implementa en un sitio central y controla puertas de enlace en los sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="3dd28-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="3dd28-106">Habilitar el desvío de medios permite que las llamadas de red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios.</span><span class="sxs-lookup"><span data-stu-id="3dd28-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="3dd28-107">Lync Server 2013 las rutas de llamadas salientes y las directivas de Enterprise Voice deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.</span><span class="sxs-lookup"><span data-stu-id="3dd28-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="3dd28-p102">Las redes Wi-Fi suelen tener más pérdidas de paquetes que las redes por cable. En general, las puertas de enlace no pueden asumir la recuperación de la pérdida de paquetes. Por lo tanto, antes de decidir si debe habilitarse el desvío de medios para una subred inalámbrica, se recomienda evaluar la calidad de una red Wi-Fi. La reducción de latencia presenta unas contrapartidas respecto a la recuperación de pérdida de paquetes que también deben tenerse en cuenta. RTAudio, un códec disponible para llamadas que no desvían el servidor de mediación, es más apropiado para ocuparse de la pérdida de paquetes.</span><span class="sxs-lookup"><span data-stu-id="3dd28-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="3dd28-113">Una vez que se haya implementado la estructura de Enterprise Voice, la planeación de la omisión de medios es sencilla.</span><span class="sxs-lookup"><span data-stu-id="3dd28-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="3dd28-114">Si tiene una topología centralizada sin vínculos WAN a redes de sucursal, puede habilitar un desvío de medios global porque no se necesita control ajustado.</span><span class="sxs-lookup"><span data-stu-id="3dd28-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="3dd28-115">Si tiene una topología distribuida compuesta de una o más regiones de red y sus sitios de sucursal afiliados, determine los aspectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3dd28-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="3dd28-116">Si los homólogos del servidor de mediación pueden asumir las capacidades que se requieren para el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="3dd28-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="3dd28-117">Los sitios de cada región de redes que están bien conectados.</span><span class="sxs-lookup"><span data-stu-id="3dd28-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="3dd28-118">La combinación de desvío de medios y control de admisión de llamadas que es apropiada para la red.</span><span class="sxs-lookup"><span data-stu-id="3dd28-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="3dd28-p103">Al habilitar el desvío de medios, se genera automáticamente un identificador de desvío único para una región de red y para todos los sitios de red que no tengan restricciones de ancho de banda en dicha región. A los sitios con restricciones de ancho de banda dentro de la región y a los sitios conectados a la región mediante vínculos WAN con restricciones de ancho de banda se les asignan sus propios identificadores de desvío únicos.</span><span class="sxs-lookup"><span data-stu-id="3dd28-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="3dd28-121">Cuando un usuario realiza una llamada a la RTC, el servidor de mediación compara el identificador de omisión de la subred del cliente con el identificador de omisión de la subred de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3dd28-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="3dd28-122">Si los dos identificadores de desvío coinciden, se usará el desvío de medios para la llamada.</span><span class="sxs-lookup"><span data-stu-id="3dd28-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="3dd28-123">Si los identificadores de omisión no coinciden, los medios de la llamada deben fluir a través del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3dd28-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="3dd28-124">Cuando un usuario recibe una llamada de la RTC, el cliente del usuario compara su identificador de desvío con el de la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="3dd28-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="3dd28-125">Si los dos identificadores de omisión coinciden, los medios se transmiten directamente de la puerta de enlace al cliente, omitiendo el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3dd28-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="3dd28-126">Solo los clientes y dispositivos de Lync 2010 o posterior admiten interacciones de omisión de medios con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="3dd28-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3dd28-p106">Además de habilitar el desvío de medios de manera global, debe habilitarse en cada tronco RTC. Si el desvío se habilita globalmente pero no se habilita en un determinado tronco RTC, no se invocará el desvío de medios en ninguna de las llamadas en las que intervenga ese tronco RTC. Asimismo, si el desvío de medios se define en <STRONG>Usar información de región y sitio</STRONG>, todas las subredes enrutables deben asociarse con los sitios en los que se ubican. Si en un sitio hay subredes enrutables en las que no se desea habilitar el desvío, dichas subredes deben agruparse en un sitio nuevo antes de habilitar el desvío de medios. Esta acción asegurará que las subredes no enrutables tengan asignado un identificador de desvío diferente.</span><span class="sxs-lookup"><span data-stu-id="3dd28-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3dd28-132">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3dd28-132">See Also</span></span>


[<span data-ttu-id="3dd28-133">Modos de omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dd28-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="3dd28-134">Omisión de medios y control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dd28-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="3dd28-135">Requisitos técnicos para la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dd28-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

