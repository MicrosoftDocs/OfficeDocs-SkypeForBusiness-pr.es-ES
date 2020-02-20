---
title: 'Lync Server 2013: Planeación de la resistencia de la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16ca49b8548b60fce6adb723f5a4546ad1ff7388
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="5ea81-102">Planeación de la resistencia de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea81-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ea81-103">_**Última modificación del tema:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="5ea81-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="5ea81-104">La resistencia de voz se refiere a la capacidad de los usuarios para seguir realizando y recibir llamadas si un sitio central que hospeda Lync Server 2013 deja de estar disponible, ya sea a través de un error de red de área extensa (WAN) u otra causa.</span><span class="sxs-lookup"><span data-stu-id="5ea81-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="5ea81-105">Si se produce un error en un sitio central, el servicio de Telefonía IP empresarial debe continuar sin interrupciones a través de la conmutación por error sin problemas al sitio de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5ea81-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="5ea81-106">En caso de error de red WAN, las llamadas de sitios de sucursal deben redirigirse a una puerta de enlace RTC local.</span><span class="sxs-lookup"><span data-stu-id="5ea81-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="5ea81-107">En esta sección se analiza la planeación de la resistencia de voz en el caso de error de sitio central o de red WAN.</span><span class="sxs-lookup"><span data-stu-id="5ea81-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5ea81-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ea81-108">In This Section</span></span>

  - [<span data-ttu-id="5ea81-109">Planeación de resistencia de voz de sitio central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea81-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="5ea81-110">Planeación de la resistencia de voz en sitios de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ea81-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

