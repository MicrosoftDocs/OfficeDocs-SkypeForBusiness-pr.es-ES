---
title: Migrar múltiples sitios y grupos de servidores
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ff9164dcd824d6b836577b04783954cb81b067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="7eafc-102">Migrar múltiples sitios y grupos de servidores</span><span class="sxs-lookup"><span data-stu-id="7eafc-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eafc-103">_**Última modificación del tema:** 2012-08-26_</span><span class="sxs-lookup"><span data-stu-id="7eafc-103">_**Topic Last Modified:** 2012-08-26_</span></span>

<span data-ttu-id="7eafc-104">Lync Server 2013 admite implementaciones de varios sitios y de varios grupos.</span><span class="sxs-lookup"><span data-stu-id="7eafc-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="7eafc-105">El proceso de migración de varios grupos desde Office Communications Server 2007 R2 a Lync Server 2013 requiere las siguientes consideraciones:</span><span class="sxs-lookup"><span data-stu-id="7eafc-105">The process of migrating multiple pools from Office Communications Server 2007 R2 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="7eafc-106">Después de implementar un grupo piloto de Lync Server 2013, debe definir un subconjunto de usuarios piloto que se moverá al grupo de Lync Server 2013 y una metodología para validar la funcionalidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7eafc-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span>

2.  <span data-ttu-id="7eafc-107">Después de implementar un servidor perimetral en la agrupación piloto, debe validar que los usuarios externos puedan comunicarse con el grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7eafc-107">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="7eafc-108">Después de realizar la transición de las rutas federadas de los servidores perimetrales de Office Communications Server 2007 R2 a los servidores perimetrales piloto de Lync Server 2013, debe validar que los usuarios federados puedan comunicarse con el grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7eafc-108">After transitioning the federated routes from Office Communications Server 2007 R2 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="7eafc-109">Después de mover todos los usuarios y los objetos de contacto que no son de usuario, debe validar que el grupo de Office Communications Server 2007 R2 está vacío.</span><span class="sxs-lookup"><span data-stu-id="7eafc-109">After moving all the users and non-user contact objects, you need to validate that the Office Communications Server 2007 R2 pool is empty.</span></span>

5.  <span data-ttu-id="7eafc-110">Después de comprobar que el grupo de Office Communications Server 2007 R2 está vacío, puede desactivar el grupo.</span><span class="sxs-lookup"><span data-stu-id="7eafc-110">After verifying that the Office Communications Server 2007 R2 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="7eafc-111">Para obtener más información sobre cómo desactivar el grupo heredado de Office Communications Server 2007 R2 y los servidores, consulte la [fase 10: retirar el sitio heredado](phase-10-decommission-legacy-site.md).</span><span class="sxs-lookup"><span data-stu-id="7eafc-111">For details about how to deactivate the legacy Office Communications Server 2007 R2 pool and servers, see [Phase 10: Decommission legacy site](phase-10-decommission-legacy-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

