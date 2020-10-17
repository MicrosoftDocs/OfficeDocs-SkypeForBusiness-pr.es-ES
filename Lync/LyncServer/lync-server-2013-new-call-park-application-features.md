---
title: 'Lync Server 2013: nuevas características de aplicación de estacionamiento de llamadas'
description: 'Lync Server 2013: nuevas características de aplicación de estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Call Park application features
ms:assetid: bddff13c-92cc-47fd-bfd4-6e8bfbfed11b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412927(v=OCS.15)
ms:contentKeyID: 48185277
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a000fc288a920773b0dc1e4a7e8fe1fb20fbb3dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561296"
---
# <a name="new-call-park-application-features-in-lync-server-2013"></a><span data-ttu-id="99d11-103">Nuevas características de aplicación de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99d11-103">New Call Park application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99d11-104">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="99d11-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="99d11-105">La aplicación de estacionamiento de llamadas permite a los usuarios de Enterprise Voice poner una llamada en espera y, a continuación, recuperarla más adelante desde cualquier teléfono.</span><span class="sxs-lookup"><span data-stu-id="99d11-105">The Call Park application makes it possible for Enterprise Voice users to put a call on hold and then retrieve it later from any phone.</span></span> <span data-ttu-id="99d11-106">El usuario que ha estacionado la llamada puede marcar el número de órbita que proporciona el parque de llamadas para recuperar la llamada estacionada o usar un mecanismo externo, como la mensajería instantánea (mi) o un sistema de paginación, para pedir a otra persona que recupere la llamada.</span><span class="sxs-lookup"><span data-stu-id="99d11-106">The user who parked the call can either dial the orbit number provided by Call Park to retrieve the parked call or use an external mechanism, such as instant messaging (IM) or a paging system, to ask someone else to retrieve the call.</span></span>

<span data-ttu-id="99d11-107">Lync Server 2013 proporciona nuevos mecanismos de recuperación ante desastres en forma de procesos de conmutación por error y conmutación por recuperación.</span><span class="sxs-lookup"><span data-stu-id="99d11-107">Lync Server 2013 provides new disaster recovery mechanisms in the form of failover and failback processes.</span></span> <span data-ttu-id="99d11-108">Estos procesos de conmutación por error y conmutación por recuperación admiten la recuperación de la funcionalidad de estacionamiento de llamadas al permitir a los usuarios hospedados en el grupo principal aprovechar la aplicación de estacionamiento de llamadas del grupo de copia de seguridad cuando se produce una interrupción en el grupo principal.</span><span class="sxs-lookup"><span data-stu-id="99d11-108">These failover and failback processes support recovery of Call Park functionality by allowing users who are homed in the primary pool to leverage the Call Park application of the backup pool when an outage occurs in the primary pool.</span></span> <span data-ttu-id="99d11-109">La compatibilidad con la recuperación ante desastres de la aplicación de estacionamiento de llamadas está habilitada como parte de la configuración y la implementación de grupos de servidores front-end emparejados.</span><span class="sxs-lookup"><span data-stu-id="99d11-109">Support for disaster recovery of the Call Park application is enabled as part of the configuration and deployment of paired Front End pools.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="99d11-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99d11-110">See Also</span></span>


[<span data-ttu-id="99d11-111">Planeación del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99d11-111">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

