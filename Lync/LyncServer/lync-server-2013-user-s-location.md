---
title: 'Lync Server 2013: Ubicación del usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d18ef5092f0506951dd9b431c6a44945b87b7f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="c6efc-102">Ubicación del usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6efc-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6efc-103">_**Última modificación del tema:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="c6efc-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="c6efc-104">El enrutamiento basado en ubicación aprovecha las mismas regiones de red, sitios y subredes que se definen en Lync Server usado por E9-1-1, CAC y media bypass para aplicar restricciones de enrutamiento de llamadas para evitar el desvío de peajes RTC.</span><span class="sxs-lookup"><span data-stu-id="c6efc-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="c6efc-105">La ubicación de un usuario se determina en función de la subred IP de los puntos de conexión de Lync del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6efc-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="c6efc-106">Cada subred IP está asociada a un sitio de red, que se agrega a las regiones de red definidas por el administrador.</span><span class="sxs-lookup"><span data-stu-id="c6efc-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="c6efc-107">El enrutamiento basado en ubicación se aplica en función del sitio de red del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6efc-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="c6efc-108">Las reglas de enrutamiento basadas en ubicación se aplican por sitio de red, lo que significa que se aplicará un conjunto determinado de reglas a todos los extremos habilitados para el enrutamiento basado en ubicación que se encuentran en el mismo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="c6efc-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="c6efc-109">Los administradores pueden aplicar el enrutamiento basado en ubicación a los sitios de red que lo necesiten.</span><span class="sxs-lookup"><span data-stu-id="c6efc-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="c6efc-110">Las directivas de enrutamiento de voz se pueden definir en cada sitio de red para definir una puerta de enlace RTC determinada que deben usar todos los usuarios ubicados en el sitio de red para llamar a números de teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="c6efc-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="c6efc-111">Estas directivas de enrutamiento de voz tendrán prioridad sobre el enrutamiento definido por la Directiva de voz del usuario cuando el usuario se encuentre en un sitio de red habilitado para el enrutamiento basado en ubicación y impedirá el enrutamiento de llamadas a través de otras puertas de enlace RTC que estén habilitadas para Enrutamiento basado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="c6efc-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="c6efc-112">Cuando un usuario de Lync coloca una llamada RTC, la Directiva de voz del usuario determina si el usuario puede tener autorización para realizar la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6efc-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="c6efc-113">Si la Directiva de voz del usuario permite al usuario realizar la llamada, el enrutamiento basado en ubicación determina la puerta de enlace RTC de la que debe salir la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6efc-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="c6efc-114">El enrutamiento basado en ubicación realiza esta determinación en función de la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="c6efc-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="c6efc-115">Una ubicación de usuario se puede clasificar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="c6efc-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="c6efc-116">El usuario se encuentra en un sitio de red conocido habilitado para el enrutamiento basado en ubicación y su número de DID (marcado interno directo) termina en una puerta de enlace RTC situada en el mismo sitio de red (por ejemplo, Office).</span><span class="sxs-lookup"><span data-stu-id="c6efc-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="c6efc-117">El enrutamiento de las llamadas salientes será a través de la Directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="c6efc-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="c6efc-118">Las llamadas RTC entrantes al usuario se enrutan a los extremos que se encuentran en el mismo sitio de red que la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="c6efc-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="c6efc-119">El usuario se encuentra en un sitio de red conocido que se encuentra en diferente del sitio de red donde se encuentra la puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="c6efc-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="c6efc-120">(es decir, el usuario ha viajado a otra oficina corporativa).</span><span class="sxs-lookup"><span data-stu-id="c6efc-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="c6efc-121">El enrutamiento de las llamadas salientes estará usando la Directiva de enrutamiento de voz del sitio de red en el que se encuentra el usuario.</span><span class="sxs-lookup"><span data-stu-id="c6efc-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="c6efc-122">Las llamadas RTC entrantes al usuario no se enrutarán a los extremos ubicados en sitios diferentes de la puerta de enlace RTC para evitar que se omitan los peajes RTC.</span><span class="sxs-lookup"><span data-stu-id="c6efc-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="c6efc-123">Cuando un usuario se encuentra en un sitio de red desconocido para la implementación de Lync Server, el enrutamiento de las llamadas salientes se basará en la Directiva de voz asignada al usuario a las puertas de enlace RTC no enlazadas con las restricciones de enrutamiento basadas en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="c6efc-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="c6efc-124">Las llamadas RTC entrantes no se enrutarán a los extremos ubicados en sitios de red desconocidos para evitar que se omitan los peajes RTC.</span><span class="sxs-lookup"><span data-stu-id="c6efc-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c6efc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6efc-125">See Also</span></span>


[<span data-ttu-id="c6efc-126">Guía para el enrutamiento basado en ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6efc-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

