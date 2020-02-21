---
title: 'Lync Server 2013: consideraciones técnicas para el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89180087909b71bc9f53f24ee02bbc077d459a17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="58ef4-102">Consideraciones técnicas sobre el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58ef4-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ef4-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="58ef4-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="58ef4-104">Al planear el enrutamiento basado en ubicación, debe tener en cuenta el impacto en los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="58ef4-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="58ef4-105">Recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="58ef4-105">Disaster Recovery</span></span>

<span data-ttu-id="58ef4-106">Durante una conmutación por error del grupo principal a un grupo de copia de seguridad, así como cuando se restauran operaciones normales en el grupo principal, el enrutamiento basado en ubicación permanece aplicado en todo momento durante un procedimiento de recuperación ante desastres.</span><span class="sxs-lookup"><span data-stu-id="58ef4-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="58ef4-107">Aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="58ef4-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="58ef4-108">La configuración del enrutamiento basado en ubicación afecta a la planificación de dónde se implementan las puertas de enlace asociadas a las aplicaciones de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="58ef4-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="58ef4-109">La puerta de enlace asociada a SBA debe estar ubicada en el mismo sitio de red que la aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios hospedados en su aplicación de sucursal con funciones de supervivencia no tendrán permiso para realizar llamadas salientes si está configurado el enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="58ef4-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="58ef4-110">Cuando la conexión WAN entre la aplicación de sucursal con funciones de supervivencia y el sitio central no esté disponible, se aplican las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="58ef4-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="58ef4-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="58ef4-111">See Also</span></span>


[<span data-ttu-id="58ef4-112">Planeación del enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58ef4-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

