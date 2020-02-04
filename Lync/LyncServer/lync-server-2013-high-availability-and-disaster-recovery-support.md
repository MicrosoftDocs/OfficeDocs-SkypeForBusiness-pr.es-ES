---
title: 'Lync Server 2013: Compatibilidad entre la alta disponibilidad y la recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73f6605f2fff063858a0180d61a306f7dd2d746
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="ede7e-102">Compatibilidad entre la alta disponibilidad y la recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede7e-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ede7e-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="ede7e-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="ede7e-104">Lync Server 2013 ofrece alta disponibilidad por redundancia de servidores a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="ede7e-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="ede7e-105">Si un servidor que ejecuta un determinado rol de servidor tiene errores, los demás servidores del grupo que ejecutan el mismo rol recogen la carga de ese servidor.</span><span class="sxs-lookup"><span data-stu-id="ede7e-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="ede7e-106">Esto es válido en servidores front-end, servidores perimetrales, servidores de mediación y directores.</span><span class="sxs-lookup"><span data-stu-id="ede7e-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="ede7e-107">Para obtener más información sobre los roles de servidor, vea [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ede7e-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="ede7e-108">Lync Server 2013 también proporciona medidas de recuperación ante desastres mediante la habilitación del emparejamiento de grupos.</span><span class="sxs-lookup"><span data-stu-id="ede7e-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="ede7e-109">Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada.</span><span class="sxs-lookup"><span data-stu-id="ede7e-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="ede7e-110">Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.</span><span class="sxs-lookup"><span data-stu-id="ede7e-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="ede7e-111">Lync Server 2013 también admite la alta disponibilidad del servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="ede7e-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="ede7e-112">Esta es una topología opcional en la que implementa dos servidores back-end para un grupo de servidores front-end y configura el reflejo sincrónico de SQL Server para todas las bases de datos de Lync que se ejecutan en los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="ede7e-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="ede7e-113">Para obtener más información sobre el emparejamiento de grupos y el reflejo de servidor, consulte [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ede7e-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ede7e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ede7e-114">See Also</span></span>


[<span data-ttu-id="ede7e-115">Roles de servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede7e-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="ede7e-116">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ede7e-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

