---
title: 'Lync Server 2013: restauración de un grupo de servidores de Lync'
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
ms.openlocfilehash: f43cbe049fdedc2f0b4d31eecc4a0506a4a62201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="ecb13-102">Restauración de un grupo de servidores de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ecb13-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecb13-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ecb13-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ecb13-104">La implementación de Lync Server puede incluir cualquiera de los siguientes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="ecb13-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="ecb13-105">Servidor front-end</span><span class="sxs-lookup"><span data-stu-id="ecb13-105">Front End Server</span></span>

  - <span data-ttu-id="ecb13-106">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ecb13-106">Mediation Server</span></span>

  - <span data-ttu-id="ecb13-107">Servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ecb13-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="ecb13-108">Servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="ecb13-108">Edge Server</span></span>

<span data-ttu-id="ecb13-109">Si todo un grupo sufre una interrupción, siga estos procedimientos para cada uno de los servidores miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="ecb13-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="ecb13-110">Para un grupo de servidores front-end, restaure primero el servidor back-end y, después, restaure cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ecb13-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="ecb13-111">Para obtener más información, consulte [restaurar un servidor de servicios de fondo de la edición empresarial en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) y [restaurar un servidor miembro de Enterprise Edition en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="ecb13-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="ecb13-112">Para todos los demás tipos de grupos, restaure cada servidor miembro.</span><span class="sxs-lookup"><span data-stu-id="ecb13-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="ecb13-113">Para obtener más información, vea [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="ecb13-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

