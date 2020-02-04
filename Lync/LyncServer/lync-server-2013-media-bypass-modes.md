---
title: 'Lync Server 2013: Modos de omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f92d45099f39ec96724f8d0f6025f58e2dbccb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41761956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="96938-102">Modos de omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96938-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96938-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="96938-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="96938-p101">Necesitas configurar la omisión de medios de forma global y para cada tronco RTC individual. Al habilitar la omisión de medios globalmente, tienes dos opciones: **Omitir siempre** y **Usar información de sitio y región**.</span><span class="sxs-lookup"><span data-stu-id="96938-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="96938-p102">Como el propio nombre sugiere, **Omitir siempre** significa que se intentará realizar la omisión de todas las llamadas de RTC. **Omitir siempre** se usa en implementaciones en las que no hay necesidad de habilitar el servicio de control de admisión de llamadas ni de especificar información detallada de configuración con respecto a cuándo intentar la omisión de medios. Además, **Omitir siempre** se usa cuando existe plena conectividad entre los clientes y las puertas de enlace RTC. En esta configuración, todas las subredes se asignan únicamente a un solo identificador de omisión, que el sistema calcula.</span><span class="sxs-lookup"><span data-stu-id="96938-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="96938-p103">Con **Usar información de sitio y región**, se usa el identificador de omisión asociado a la configuración del sitio y de la región para tomar la decisión de omisión. Esta configuración proporciona la flexibilidad de configurar la omisión de medios para las topologías más comunes, ya que proporciona un control más preciso cuando se produce la omisión, además de admitir interacciones con el servicio de control de admisión de llamadas (CAC). El sistema intenta facilitarte la tarea asignando automáticamente identificadores de omisión de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="96938-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="96938-113">El sistema asigna automáticamente un único identificador de omisión a cada región.</span><span class="sxs-lookup"><span data-stu-id="96938-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="96938-114">Cualquier sitio conectado a una región por un vínculo WAN sin restricciones de ancho de banda hereda el mismo identificador de omisión de la región.</span><span class="sxs-lookup"><span data-stu-id="96938-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="96938-115">A un sitio asociado a la región por un vínculo WAN con un ancho de banda restringido se le asigna un identificador de omisión distinto al de la región.</span><span class="sxs-lookup"><span data-stu-id="96938-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="96938-116">Las subredes asociadas a cada sitio heredan el identificador de omisión del sitio.</span><span class="sxs-lookup"><span data-stu-id="96938-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="96938-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="96938-117">See Also</span></span>


[<span data-ttu-id="96938-118">Información general sobre la omisión de elementos multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96938-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="96938-119">Omisión de medios y control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96938-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="96938-120">Requisitos técnicos para la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96938-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

