---
title: Fases de la migración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f789abee1949f7fae5a7a3d7dcdc03c86dc352
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527227"
---
# <a name="migration-phases"></a><span data-ttu-id="204d6-102">Fases de la migración</span><span class="sxs-lookup"><span data-stu-id="204d6-102">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="204d6-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="204d6-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="204d6-104">En Lync Server 2013, defina sitios en la red que contengan componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204d6-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="204d6-105">Un sitio es un conjunto de equipos que están bien conectados por una red de alta velocidad y baja latencia, como una red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="204d6-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="204d6-106">Un *grupo de servidores front-end* es un conjunto de servidores front-end configurados de manera idéntica que funcionan para ofrecer servicios para un grupo común de usuarios.</span><span class="sxs-lookup"><span data-stu-id="204d6-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="204d6-107">Un grupo de servidores proporciona escalabilidad y funciones de conmutación por error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="204d6-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="204d6-108">Cada servidor en un grupo debe ejecutar un rol o roles de servidores idénticos.</span><span class="sxs-lookup"><span data-stu-id="204d6-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="204d6-109">Un servidor Standard Edition, diseñado para pequeñas organizaciones, también define un grupo y se ejecuta en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="204d6-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="204d6-110">Esto le permite tener funcionalidad de Lync Server 2013 para un costo menor, pero no proporciona una solución de alta disponibilidad real.</span><span class="sxs-lookup"><span data-stu-id="204d6-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="204d6-111">En las siguientes fases, se describe el proceso de una migración de grupo de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="204d6-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="204d6-112">En el caso de varios sitios que contengan varios grupos, se debe seguir este enfoque por fases para cada grupo individual.</span><span class="sxs-lookup"><span data-stu-id="204d6-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="204d6-113">Fase 1: planear la migración desde Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="204d6-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="204d6-114">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="204d6-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="204d6-115">Fase 3: implementar el grupo piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="204d6-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="204d6-116">Fase 4: mover usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="204d6-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="204d6-117">Fase 5: agregar un servidor perimetral de Lync Server 2013 a un grupo piloto</span><span class="sxs-lookup"><span data-stu-id="204d6-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="204d6-118">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="204d6-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="204d6-119">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="204d6-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="204d6-120">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="204d6-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

