---
title: 'Lync Server 2013: compatibilidad de alta disponibilidad y recuperación ante desastres'
description: 'Lync Server 2013: compatibilidad de alta disponibilidad y recuperación ante desastres.'
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
ms.openlocfilehash: a8113c6b54cbb55e8149f8d6dd1b53ccbdc9436d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552796"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="d2dac-103">Compatibilidad de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2dac-103">High availability and disaster recovery support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2dac-104">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="d2dac-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="d2dac-105">Lync Server 2013 proporciona alta disponibilidad mediante la redundancia de servidores a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="d2dac-105">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="d2dac-106">Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="d2dac-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="d2dac-107">Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.</span><span class="sxs-lookup"><span data-stu-id="d2dac-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="d2dac-108">Para obtener más información sobre los roles de servidor, consulte [roles de servidor en Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d2dac-108">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="d2dac-109">Lync Server 2013 también proporciona medidas de recuperación ante desastres habilitando el emparejamiento de grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="d2dac-109">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="d2dac-110">Si implementa esta topología, designará pares de grupos front-end, con cada grupo en un par ubicado en un centro de datos separado y en un área geográfica separada.</span><span class="sxs-lookup"><span data-stu-id="d2dac-110">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="d2dac-111">Si un grupo o un sitio dejan de funcionar, puede redirigir a los usuarios del grupo para que usen el otro grupo del par, con una interrupción del servicio mínima.</span><span class="sxs-lookup"><span data-stu-id="d2dac-111">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="d2dac-112">Lync Server 2013 también admite alta disponibilidad del servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="d2dac-112">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="d2dac-113">Se trata de una topología opcional en la que se implementan dos servidores back-end para un grupo de servidores front-end y se configuran los reflejos de SQL Server sincrónicos para todas las bases de datos de Lync que se ejecutan en los servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="d2dac-113">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="d2dac-114">Para obtener más información sobre el emparejamiento de grupos y la creación de reflejos del servidor back-end, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="d2dac-114">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d2dac-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2dac-115">See Also</span></span>


[<span data-ttu-id="d2dac-116">Roles de servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2dac-116">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="d2dac-117">Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2dac-117">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

