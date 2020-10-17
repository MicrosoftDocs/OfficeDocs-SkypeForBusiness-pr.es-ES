---
title: 'Lync Server 2013: ubicación de la puerta de enlace RTC'
description: 'Lync Server 2013: ubicación de la puerta de enlace RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f793249908bd1f064f9038ddd90c7f5b01a61d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565606"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="927df-103">Ubicación de la puerta de enlace RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="927df-103">PSTN gateway's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="927df-104">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="927df-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="927df-105">Las llamadas enrutadas a través de puertas de enlace RTC y PBX pueden requerir restricciones de enrutamiento Location-Based en función de la ubicación de dichos sistemas.</span><span class="sxs-lookup"><span data-stu-id="927df-105">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="927df-106">El enrutamiento Location-Based se puede habilitar en la granularidad en función de cada tronco.</span><span class="sxs-lookup"><span data-stu-id="927df-106">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="927df-107">Enrutamiento de Location-Based introduce el siguiente conjunto de reglas cuando se habilita en un tronco:</span><span class="sxs-lookup"><span data-stu-id="927df-107">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="927df-108">Cuando se habilita Location-Based enrutamiento por tronco, las reglas definidas en ese tronco se aplicarán solo a las llamadas enrutadas a través de ese tronco.</span><span class="sxs-lookup"><span data-stu-id="927df-108">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="927df-109">Para evitar que se omitan los peajes de RTC en los que las llamadas se originan desde un sitio de red diferente que el sitio de red en el que se encuentra la puerta de enlace RTC, el enrutamiento de Location-Based introduce la Asociación de un sitio de red a un tronco determinado.</span><span class="sxs-lookup"><span data-stu-id="927df-109">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="927df-110">Define el sitio de red que permite que las llamadas se enruten a un tronco determinado.</span><span class="sxs-lookup"><span data-stu-id="927df-110">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="927df-111">Los troncos pueden habilitarse para Location-Based enrutamiento de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="927df-111">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="927df-112">El tronco se define para una puerta de enlace RTC que salida las llamadas a la RTC.</span><span class="sxs-lookup"><span data-stu-id="927df-112">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="927df-113">Las llamadas entrantes redirigidas por un tronco de este tipo se redirigirán solo a los extremos ubicados dentro del mismo sitio de red que el tronco.</span><span class="sxs-lookup"><span data-stu-id="927df-113">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="927df-114">El tronco se define para un servidor de mediación del mismo nivel que no salida las llamadas a los usuarios de RTC y servicios con teléfonos heredados en ubicaciones estáticas (es decir, los teléfonos PBX).</span><span class="sxs-lookup"><span data-stu-id="927df-114">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="927df-115">Para esta configuración específica, se considerará que todas las llamadas entrantes redirigidas por un tronco de este tipo se originan desde el mismo sitio de red que el tronco.</span><span class="sxs-lookup"><span data-stu-id="927df-115">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="927df-116">Las llamadas de los usuarios de PBX tendrán la misma aplicación de enrutamiento Location-Based que los usuarios de Lync que se encuentran en el mismo sitio de red que el tronco.</span><span class="sxs-lookup"><span data-stu-id="927df-116">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="927df-117">Si dos sistemas PBX ubicados en sitios de red independientes están conectados a través de Lync Server, Location-Based el enrutamiento permitirá el enrutamiento desde un extremo de PBX en un sitio de red a otro extremo de PBX en el otro sitio de red.</span><span class="sxs-lookup"><span data-stu-id="927df-117">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="927df-118">Este escenario no se bloqueará Location-Based enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="927df-118">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="927df-119">Además de este escenario y de una manera similar a un usuario de Lync en la misma ubicación, los extremos conectados a un puesto del servidor de mediación con esta configuración podrán realizar o recibir llamadas a y desde otros servidores de mediación que no enruten llamadas a la RTC (es decir, un extremo conectado a otro PBX), independientemente del sitio de red al que está asociado el servidor</span><span class="sxs-lookup"><span data-stu-id="927df-119">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="927df-120">Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y las llamadas reenvíos en las que participen los extremos RTC estarán sujetas a un enrutamiento basado en ubicación para usar solo puertas de enlace RTC definidas como locales para este servidor de mediación del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="927df-120">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="927df-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="927df-121">See Also</span></span>


[<span data-ttu-id="927df-122">Guía para el enrutamiento de Location-Based en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="927df-122">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

