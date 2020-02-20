---
title: Migrar varios sitios y grupos de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c1e7d104fa35cba02e95dffb348b0f64b16b66
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="e33e0-102">Migrar varios sitios y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="e33e0-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e33e0-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e33e0-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e33e0-104">Lync Server 2013 admite implementaciones de varios sitios y de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="e33e0-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="e33e0-105">El proceso de migración de varios grupos de servidores de Lync Server 2010 a Lync Server 2013 requiere las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="e33e0-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="e33e0-106">Después de implementar un grupo piloto de Lync Server 2013, debe definir un subconjunto de usuarios piloto que se trasladarán al grupo de Lync Server 2013 y una metodología para validar la funcionalidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e33e0-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="e33e0-107">Por ejemplo, después de mover un usuario al grupo piloto, compruebe que la Directiva de conferencia del usuario se ha movido a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e33e0-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="e33e0-108">Después de implementar un servidor perimetral en el grupo piloto, debe validar que los usuarios externos pueden comunicarse con el grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e33e0-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="e33e0-109">Después de realizar la transición de las rutas federadas de los servidores perimetrales de Lync Server 2010 a los servidores perimetrales de Lync Server 2013 piloto, debe validar que los usuarios federados puedan comunicarse con el grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e33e0-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="e33e0-110">Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo de servidores de Lync Server 2010 está vacío.</span><span class="sxs-lookup"><span data-stu-id="e33e0-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="e33e0-111">Después de comprobar que el grupo de servidores de Lync Server 2010 está vacío, puede desactivar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="e33e0-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="e33e0-112">Para obtener más información sobre cómo desactivar el grupo de servidores de Lync Server 2010 y los servidores heredados, vea [Phase 8: decommission Legacy pools](phase-8-decommission-legacy-pools.md).</span><span class="sxs-lookup"><span data-stu-id="e33e0-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

