---
title: 'Lync Server 2013: información general sobre el enrutamiento de Location-Based'
description: 'Lync Server 2013: información general sobre el enrutamiento de Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562816"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0884d-103">Información general sobre el enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0884d-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0884d-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0884d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0884d-105">Enrutamiento de Location-Based introduce un nuevo conjunto de reglas que modifica el enrutamiento de las llamadas RTC nacionales e internacionales para evitar la omisión de peaje.</span><span class="sxs-lookup"><span data-stu-id="0884d-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="0884d-106">El enrutamiento de Location-Based proporciona la flexibilidad necesaria para establecer el ámbito de estas reglas a regiones específicas, puertas de enlace específicas o a un conjunto específico de usuarios únicamente.</span><span class="sxs-lookup"><span data-stu-id="0884d-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="0884d-107">Los siguientes escenarios ilustran los tipos principales de restricciones Location-Based el enrutamiento puede exigir:</span><span class="sxs-lookup"><span data-stu-id="0884d-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="0884d-108">Llamadas de salida: el enrutamiento de Location-Based puede aplicar llamadas salientes a salidas de una puerta de enlace RTC que se encuentra en la misma región en la que el autor de la llamada está evitando el desvío de llamadas RTC, lo que impide que se realicen llamadas de salida de una puerta de enlace RTC situada en una región distinta como autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0884d-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="0884d-109">Llamadas de entrada: el enrutamiento de Location-Based puede evitar las llamadas RTC entrantes para llamar a los puntos de conexión de Lync si el enrutamiento de la puerta de enlace RTC la llamada entrante no se encuentra en la misma región que el usuario de Lync llamado.</span><span class="sxs-lookup"><span data-stu-id="0884d-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="0884d-110">Regiones desconocidas: el enrutamiento de Location-Based restringe las llamadas RTC entrantes y salientes a los usuarios que se encuentran en ubicaciones indeterminadas (por ejemplo, los usuarios remotos que se conectan desde Internet o que se encuentran en regiones desconocidas).</span><span class="sxs-lookup"><span data-stu-id="0884d-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="0884d-111">Regiones internacionales: el enrutamiento de Location-Based fuerza el enrutamiento de las llamadas salientes a través de puertas de enlace RTC internacionales Si no se encuentra una puerta de enlace local a la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="0884d-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0884d-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0884d-112">See Also</span></span>


[<span data-ttu-id="0884d-113">Planeación del enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0884d-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

