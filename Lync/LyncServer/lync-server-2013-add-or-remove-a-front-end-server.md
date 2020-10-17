---
title: 'Lync Server 2013: agregar o quitar un servidor front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f30eb0034df6b0783f8389d69841a338c90effd4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521477"
---
# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="ae606-102">Agregar o quitar un servidor front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae606-102">Add or remove a Front End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae606-103">_**Última modificación del tema:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="ae606-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="ae606-p101">Cuando agrega un servidor front-end a un grupo o cuando quita un servidor front-end de un grupo, debe reiniciar el grupo. Para evitar interrupciones del servicio para los usuarios, use el siguiente procedimiento al agregar o quitar un servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ae606-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae606-106">Si va a agregar nuevos servidores al grupo, actualice los nuevos servidores de grupo para que estén en el mismo nivel de actualización acumulativa que los servidores existentes en el grupo.</span><span class="sxs-lookup"><span data-stu-id="ae606-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="ae606-107">Para agregar o quitar servidores front-end</span><span class="sxs-lookup"><span data-stu-id="ae606-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="ae606-p102">Si desea quitar servidores front-end, primero detenga las nuevas conexiones a esos servidores. Para ello, puede usar el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ae606-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="ae606-110">Cuando los servidores que se quitará no tienen sesiones actuales, detenga los servicios de Lync Server en esos servidores.</span><span class="sxs-lookup"><span data-stu-id="ae606-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="ae606-111">Abra el Generador de topologías, y agregue o quite los servidores necesarios.</span><span class="sxs-lookup"><span data-stu-id="ae606-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="ae606-112">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="ae606-112">Publish the topology.</span></span>

5.  <span data-ttu-id="ae606-113">Si el grupo de servidores front-end ha pasado de tener dos servidores front-end a más de dos o ha ido de más de dos servidores a dos exactamente, debe escribir el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ae606-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="ae606-114">Si el grupo tiene tres o más servidores, debe haber al menos tres de esos servidores en ejecución cuando escriba este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ae606-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="ae606-115">Reinicie todos los servidores front-end del grupo, uno por vez.</span><span class="sxs-lookup"><span data-stu-id="ae606-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

