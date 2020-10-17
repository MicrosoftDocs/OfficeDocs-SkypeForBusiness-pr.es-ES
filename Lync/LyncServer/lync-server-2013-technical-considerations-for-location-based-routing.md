---
title: 'Lync Server 2013: consideraciones técnicas para el enrutamiento Location-Based'
description: 'Lync Server 2013: consideraciones técnicas para el enrutamiento de Location-Based.'
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
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568056"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d1b0b-103">Consideraciones técnicas sobre el enrutamiento Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1b0b-103">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1b0b-104">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d1b0b-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d1b0b-105">Al planear Location-Based el enrutamiento, debe tener en cuenta el impacto en los siguientes escenarios.</span><span class="sxs-lookup"><span data-stu-id="d1b0b-105">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="d1b0b-106">Recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="d1b0b-106">Disaster Recovery</span></span>

<span data-ttu-id="d1b0b-107">Durante una conmutación por error del grupo principal a un grupo de copia de seguridad, así como cuando se restauran operaciones normales en el grupo principal, Location-Based el enrutamiento se aplica en todo momento durante un proceso de recuperación y desastre.</span><span class="sxs-lookup"><span data-stu-id="d1b0b-107">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="d1b0b-108">Aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="d1b0b-108">Survivable Branch Appliance</span></span>

<span data-ttu-id="d1b0b-109">La configuración del enrutamiento de Location-Based afecta a la planeación de la ubicación en la que se implementan las puertas de enlace asociadas a las aplicaciones de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d1b0b-109">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="d1b0b-110">La puerta de enlace asociada a SBA debe estar ubicada en el mismo sitio de red que la aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios hospedados en su aplicación de sucursal con funciones de supervivencia no podrán realizar llamadas salientes si se configura Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d1b0b-110">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="d1b0b-111">Cuando la conexión WAN entre la aplicación de sucursal con funciones de supervivencia y el sitio central no está disponible, se aplican Location-Based restricciones de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d1b0b-111">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1b0b-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1b0b-112">See Also</span></span>


[<span data-ttu-id="d1b0b-113">Planeación del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1b0b-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

