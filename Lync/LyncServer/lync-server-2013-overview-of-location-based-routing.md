---
title: 'Lync Server 2013: información general sobre el enrutamiento basado en la ubicación'
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
ms.openlocfilehash: 07a7db57d506b892fd030efccfb304c7103e1e9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="50c4d-102">Información general sobre el enrutamiento basado en la ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50c4d-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50c4d-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="50c4d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="50c4d-p101">El enrutamiento basado en ubicación introduce un nuevo conjunto de reglas que modifica el enrutamiento de llamadas RTC nacionales e internacionales para evitar que se omitan los números de pago. El enrutamiento basado en ubicación proporciona la flexibilidad para delimitar estas reglas solo a regiones específicas, a puertas de enlace específicas o a un conjunto específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="50c4d-p101">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass. Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="50c4d-106">Los siguientes escenarios ilustran los tipos principales de restricciones que el enrutamiento basado en ubicación puede exigir:</span><span class="sxs-lookup"><span data-stu-id="50c4d-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="50c4d-107">Llamadas de salida: el enrutamiento basado en la ubicación puede exigir llamadas salientes a salidas de una puerta de enlace RTC que se encuentra en la misma región, en la que la persona que llama está evitando el omisión de llamadas RTC, lo que evita que se produzcan salidas de una puerta de enlace RTC situada en otra región, como el llamadas.</span><span class="sxs-lookup"><span data-stu-id="50c4d-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="50c4d-108">Llamadas de entrada: el enrutamiento basado en la ubicación puede evitar llamadas RTC entrantes para llamar a puntos de conexión de Lync si el enrutamiento de la puerta de enlace RTC la llamada entrante no se encuentra en la misma región que la llamada usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="50c4d-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="50c4d-109">Regiones desconocidas: el enrutamiento basado en la ubicación restringe las llamadas a través de la RTC entrantes y salientes a los usuarios que se encuentran en ubicaciones indeterminadas (es decir, los usuarios remotos se conectan desde Internet o se encuentran en regiones desconocidas).</span><span class="sxs-lookup"><span data-stu-id="50c4d-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="50c4d-110">Regiones internacionales: el enrutamiento basado en la ubicación exige el enrutamiento de llamadas salientes a través de puertas de enlace RTC internacionales Si no se puede encontrar una puerta de enlace local a la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="50c4d-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="50c4d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="50c4d-111">See Also</span></span>


[<span data-ttu-id="50c4d-112">Planificar el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50c4d-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

