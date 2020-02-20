---
title: 'Lync Server 2013: restauración de un grupo de servidores de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f9bc8e86b4dcdbd74d9fd9eed11de9c3735520e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="d8989-102">Restauración de un grupo de servidores de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8989-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8989-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="d8989-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="d8989-104">La implementación de Lync Server puede incluir cualquiera de los siguientes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="d8989-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="d8989-105">Servidor front-end</span><span class="sxs-lookup"><span data-stu-id="d8989-105">Front End Server</span></span>

  - <span data-ttu-id="d8989-106">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d8989-106">Mediation Server</span></span>

  - <span data-ttu-id="d8989-107">Servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d8989-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="d8989-108">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="d8989-108">Edge Server</span></span>

<span data-ttu-id="d8989-109">Si un grupo completo experimenta una interrupción, siga estos procedimientos para cada servidor miembro del grupo.</span><span class="sxs-lookup"><span data-stu-id="d8989-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="d8989-110">Para un grupo de servidores front-end, restaure el servidor back-end en primer lugar y, a continuación, restaure cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d8989-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="d8989-111">Para obtener más información, consulte [restaurar un servidor back-end de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) y [restaurar un servidor miembro de Enterprise Edition en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="d8989-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="d8989-112">En el resto de tipos de grupos, restaure cada uno de los servidores miembro.</span><span class="sxs-lookup"><span data-stu-id="d8989-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="d8989-113">Para obtener más información, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="d8989-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

