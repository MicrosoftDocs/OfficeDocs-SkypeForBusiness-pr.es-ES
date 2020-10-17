---
title: 'Lync Server 2013: componentes necesarios para el director'
description: 'Lync Server 2013: componentes necesarios para el director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f717b9ddb9557f212321cdab075713a4b85c2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549506"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="eecf9-103">Componentes necesarios para el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eecf9-103">Components required for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eecf9-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="eecf9-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="eecf9-105">El único componente necesario para crear y configurar un director es implementar el rol de servidor Director.</span><span class="sxs-lookup"><span data-stu-id="eecf9-105">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="eecf9-106">Para ello, puede usar el generador de topologías y definir un grupo de un solo equipo o un grupo de varios equipos en el nodo de grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="eecf9-106">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="eecf9-107">Una vez que haya definido el director o el grupo de directores, ejecute el Asistente para la implementación de Lync Server en el equipo que será director.</span><span class="sxs-lookup"><span data-stu-id="eecf9-107">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="eecf9-108">En el caso de un grupo de directores, ejecute el Asistente para la implementación de Lync Server en cada servidor que vaya a ser miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="eecf9-108">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="eecf9-109">Topologías</span><span class="sxs-lookup"><span data-stu-id="eecf9-109">Topologies</span></span>

<span data-ttu-id="eecf9-110">Puede implementar un servidor de Director único o un grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="eecf9-110">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="eecf9-111">El director es siempre un servidor o grupo de servidores independiente, no combinado con ningún otro rol de servidor en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eecf9-111">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eecf9-112">Si no implementa los directores, el servidor front-end o el grupo de servidores front-end asumirán el rol de director.</span><span class="sxs-lookup"><span data-stu-id="eecf9-112">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="eecf9-113">Un grupo de directores debe tener carga equilibrada.</span><span class="sxs-lookup"><span data-stu-id="eecf9-113">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="eecf9-114">Puede hacer uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="eecf9-114">You can do one of the following:</span></span>

  - <span data-ttu-id="eecf9-115">Cree una topología que use un equilibrador de carga de hardware para los servicios web y el equilibrio de carga del sistema de nombres de dominio (DNS) para los otros tipos de tráfico.</span><span class="sxs-lookup"><span data-stu-id="eecf9-115">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="eecf9-116">Grupo de Director escalado-equilibrio de carga de DNS y equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eecf9-116">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="eecf9-117">Cree una topología que use un equilibrador de carga de hardware para el equilibrio de carga necesario para el grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="eecf9-117">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="eecf9-118">Grupo de Director escalado-equilibrador de carga de hardware en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eecf9-118">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

