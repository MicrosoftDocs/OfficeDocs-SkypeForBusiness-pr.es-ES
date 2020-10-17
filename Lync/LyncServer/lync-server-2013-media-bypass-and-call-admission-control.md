---
title: 'Lync Server 2013: omisión de medios y control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4afa8f26e28fbb4261b0d8524c02efeb8d2a3132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524637"
---
# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e35dd-102">Omisión de medios y control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e35dd-102">Media bypass and call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e35dd-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="e35dd-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="e35dd-104">El desvío de medios y el control de admisión de llamadas (CAC) funcionan juntos para administrar el control del ancho de banda para los medios de llamada.</span><span class="sxs-lookup"><span data-stu-id="e35dd-104">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media.</span></span> <span data-ttu-id="e35dd-105">La omisión de medios facilita el flujo de medios a través de vínculos bien conectados; El CAC administra el tráfico en vínculos con restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="e35dd-105">Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints.</span></span> <span data-ttu-id="e35dd-106">Dado que la omisión de medios y el CAC son mutuamente excluyentes, debe estar atento a uno cuando Planee la otra.</span><span class="sxs-lookup"><span data-stu-id="e35dd-106">Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other.</span></span> <span data-ttu-id="e35dd-107">Se admiten las siguientes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="e35dd-107">The following combinations are supported:</span></span>

  - <span data-ttu-id="e35dd-108">El CAC y el desvío de medios están habilitados.</span><span class="sxs-lookup"><span data-stu-id="e35dd-108">CAC and Media Bypass are both enabled.</span></span> <span data-ttu-id="e35dd-109">La omisión de medios debe estar configurada para **usar la información de sitio y región**.</span><span class="sxs-lookup"><span data-stu-id="e35dd-109">Media Bypass must be set to **Use Site and Region Information**.</span></span> <span data-ttu-id="e35dd-110">Esta información de sitio y región es la misma que la usada para CAC.</span><span class="sxs-lookup"><span data-stu-id="e35dd-110">This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="e35dd-111">Si habilita el CAC, no podrá seleccionar **omitir siempre**y viceversa, ya que las dos configuraciones se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="e35dd-111">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive.</span></span> <span data-ttu-id="e35dd-112">Es decir, solo una de las dos se aplicará a una llamada RTC determinada.</span><span class="sxs-lookup"><span data-stu-id="e35dd-112">That is, only one of the two will apply to any given PSTN call.</span></span> <span data-ttu-id="e35dd-113">En primer lugar, se realiza una comprobación para determinar si la omisión de medios se aplica a la llamada.</span><span class="sxs-lookup"><span data-stu-id="e35dd-113">First, a check is made to determine if media bypass applies to the call.</span></span> <span data-ttu-id="e35dd-114">Si es así, no se usará el CAC.</span><span class="sxs-lookup"><span data-stu-id="e35dd-114">If it does, then CAC is not used.</span></span> <span data-ttu-id="e35dd-115">Esto tiene sentido, porque si una llamada es apta para la omisión, es por definición usando una conexión donde no se necesita el CAC.</span><span class="sxs-lookup"><span data-stu-id="e35dd-115">This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed.</span></span> <span data-ttu-id="e35dd-116">Si no se puede aplicar el método bypass a la llamada (es decir, si no coinciden los identificadores de omisión del cliente y la puerta de enlace), se aplicará el CAC a la llamada.</span><span class="sxs-lookup"><span data-stu-id="e35dd-116">If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="e35dd-117">CAC no habilitado y desvío de medios configurado para **omitir siempre**.</span><span class="sxs-lookup"><span data-stu-id="e35dd-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="e35dd-118">En esta configuración, las subredes de cliente y de tronco están asignadas a un solo identificador de omisión, calculado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="e35dd-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="e35dd-119">CAC no habilitado y el desvío de medios configurado para **usar la información de sitio y región**.</span><span class="sxs-lookup"><span data-stu-id="e35dd-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="e35dd-120">Cuando se habilita **usar información de sitio y región** , la determinación por omisión funciona esencialmente de la misma manera, independientemente de si CAC está habilitado o no.</span><span class="sxs-lookup"><span data-stu-id="e35dd-120">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not.</span></span> <span data-ttu-id="e35dd-121">Es decir, para cualquier llamada RTC, la subred del cliente se asigna a un sitio en particular y se extrae el identificador de omisión de esa subred.</span><span class="sxs-lookup"><span data-stu-id="e35dd-121">That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="e35dd-122">De forma similar, la subred de la puerta de enlace se asigna a un sitio en particular y se extrae el identificador de omisión de dicha subred.</span><span class="sxs-lookup"><span data-stu-id="e35dd-122">Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="e35dd-123">Solo si los dos identificadores de omisión son idénticos, se omitirá la llamada.</span><span class="sxs-lookup"><span data-stu-id="e35dd-123">Only if the two bypass IDs are identical will bypass happen for the call.</span></span> <span data-ttu-id="e35dd-124">Si no son idénticos, no se producirá la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="e35dd-124">If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="e35dd-125">Aunque el CAC está deshabilitado globalmente, es necesario definir la Directiva de ancho de banda para cada sitio y vínculo si desea usar la configuración de sitio y región para controlar la decisión de omisión.</span><span class="sxs-lookup"><span data-stu-id="e35dd-125">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision.</span></span> <span data-ttu-id="e35dd-126">El valor real de la restricción de ancho de banda o su modalidad no importa.</span><span class="sxs-lookup"><span data-stu-id="e35dd-126">The actual value of the bandwidth constraint or its modality doesn’t matter.</span></span> <span data-ttu-id="e35dd-127">El objetivo final es hacer que el sistema calcule automáticamente distintos identificadores de omisión para asociarlos con distintas configuraciones regionales que no estén bien conectadas.</span><span class="sxs-lookup"><span data-stu-id="e35dd-127">The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected.</span></span> <span data-ttu-id="e35dd-128">Definir una restricción de ancho de banda por definición significa que un vínculo no está bien conectado.</span><span class="sxs-lookup"><span data-stu-id="e35dd-128">Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="e35dd-129">El CAC está habilitado y la omisión de medios no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e35dd-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="e35dd-130">Esto sólo se aplicará cuando todas las puertas de enlace y IP-PBXs no estén bien conectados o no cumplan otros requisitos para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="e35dd-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="e35dd-131">Para obtener más información sobre los requisitos para la omisión de medios, consulte [Technical Requirements for Media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="e35dd-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e35dd-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e35dd-132">See Also</span></span>


[<span data-ttu-id="e35dd-133">Información general sobre la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e35dd-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="e35dd-134">Modos de omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e35dd-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="e35dd-135">Requisitos técnicos para la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e35dd-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

