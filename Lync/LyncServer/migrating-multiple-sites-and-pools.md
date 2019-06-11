---
title: Migrar múltiples sitios y grupos de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7759c52051dfe4ca4a46e105e6a33f3284f334e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="45217-102">Migrar múltiples sitios y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="45217-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45217-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="45217-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="45217-104">Lync Server 2013 admite implementaciones de varios sitios y de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="45217-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="45217-105">El proceso de migración de varios grupos de Lync Server 2010 a Lync Server 2013 requiere las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="45217-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="45217-106">Después de implementar un grupo piloto de Lync Server 2013, debe definir un subconjunto de usuarios piloto que se moverá al grupo de Lync Server 2013 y una metodología para validar la funcionalidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="45217-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="45217-107">Por ejemplo, después de mover un usuario a la agrupación piloto, compruebe que la Directiva de conferencia del usuario se ha movido a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45217-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="45217-108">Después de implementar un servidor perimetral en la agrupación piloto, debe validar que los usuarios externos puedan comunicarse con el grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="45217-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="45217-109">Después de realizar la transición de las rutas federadas de los servidores perimetrales de Lync Server 2010 a los servidores perimetrales de Lync Server 2013 piloto, debe validar que los usuarios federados puedan comunicarse con el grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="45217-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="45217-110">Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo de servidores de Lync Server 2010 está vacío.</span><span class="sxs-lookup"><span data-stu-id="45217-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="45217-111">Después de comprobar que el grupo de Lync Server 2010 está vacío, puede desactivar el grupo.</span><span class="sxs-lookup"><span data-stu-id="45217-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="45217-112">Para obtener más información sobre cómo desactivar el grupo de servidores y los servidores de Lync Server 2010, consulte la [fase 8:](phase-8-decommission-legacy-pools.md)demuestre los grupos heredados.</span><span class="sxs-lookup"><span data-stu-id="45217-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

