---
title: 'Lync Server 2013: Omisión de medios y control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3cc26-102">Omisión de medios y control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cc26-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc26-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3cc26-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3cc26-p101">El servicio de control de admisión de llamadas (CAC) y la omisión de medios funcionan conjuntamente para administrar el control del ancho de banda para medios telefónicos. La omisión de medios facilita el flujo de medios a través de vínculos con buenas conexiones; el CAC administra el tráfico en vínculos con restricciones de ancho de banda. Como la omisión de medios y el CAC son mutuamente exclusivos, deberás tener en cuenta a cada uno de ellos al realizar la planificación del otro. Se admiten las siguientes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="3cc26-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="3cc26-p102">Tanto el CAC como la omisión de medios están habilitados. La omisión de medios necesita estar configurada con **Usar información de sitio y región**. La información de sitio y región es la misma que la usada para el CAC.</span><span class="sxs-lookup"><span data-stu-id="3cc26-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="3cc26-p103">Si habilitas el CAC, no podrás seleccionar **Omitir siempre**, y viceversa, ya que las dos configuraciones son mutuamente exclusivas; es decir, solo se aplicará una de las dos a una llamada RTC determinada. En primer lugar, se realiza una comprobación para determinar si se aplica la omisión de medios a la llamada. Si es así, no se usa el CAC. Es lógico, ya que si una llamada reúne las condiciones necesarias para la omisión, está usando, por definición, una conexión que no requiere el servicio de control de admisión de llamadas. Si no puede aplicarse la omisión a la llamada (es decir, si los identificadores de omisión del cliente y de la puerta de enlace no coinciden), se aplicará el CAC a la llamada.</span><span class="sxs-lookup"><span data-stu-id="3cc26-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="3cc26-117">CAC no habilitado y la omisión de medios configurada con **Omitir siempre**.</span><span class="sxs-lookup"><span data-stu-id="3cc26-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="3cc26-118">En esta configuración, las subredes tanto del tronco como del cliente están asignadas a un solo identificador de omisión, y el sistema lo calcula.</span><span class="sxs-lookup"><span data-stu-id="3cc26-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="3cc26-119">CAC no habilitado y la omisión de medios configurada con **Usar información de sitio y región**.</span><span class="sxs-lookup"><span data-stu-id="3cc26-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="3cc26-p104">Cuando **Usar información de sitio y región** está habilitado, la determinación de omisión funciona básicamente del mismo modo, independientemente de si el CAC está habilitado o no. Es decir, para todas las llamadas RTC, la subred del cliente está asignada a un sitio en particular, y se extrae el identificador de omisión para dicha subred. Del mismo modo, la subred de la puerta de enlace está asignada a un sitio en particular, y se extrae el identificador de omisión para dicha subred. La omisión de la llamada solo se producirá si los dos identificadores de omisión son idénticos. Si no es así, la omisión de medios no tendrá lugar.</span><span class="sxs-lookup"><span data-stu-id="3cc26-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="3cc26-p105">Incluso aunque el CAC esté deshabilitado globalmente, es necesario definir la directiva de ancho de banda para cada uno de los sitios y vínculos si deseas usar una configuración de sitio y región para controlar la decisión de omisión. El valor real de la restricción de ancho de banda o su modalidad no es relevante. El objetivo final es hacer que el sistema calcule automáticamente diferentes identificadores de omisión para asociarse con diferentes configuraciones regionales que no tienen una buena conexión. La definición de una restricción de ancho de banda significa por definición que un vínculo no tiene una buena conexión.</span><span class="sxs-lookup"><span data-stu-id="3cc26-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="3cc26-129">El CAC está habilitado y la omisión de medios no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="3cc26-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="3cc26-130">Esto se aplica únicamente cuando todas las puertas de enlace y las IP-PBX presentan una conexión deficiente o no reúnen otros requisitos para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="3cc26-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="3cc26-131">Para obtener más información sobre los requisitos para la omisión de multimedia, consulte [requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="3cc26-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3cc26-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cc26-132">See Also</span></span>


[<span data-ttu-id="3cc26-133">Información general sobre la omisión de elementos multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cc26-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="3cc26-134">Modos de omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cc26-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="3cc26-135">Requisitos técnicos para la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cc26-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

