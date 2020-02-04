---
title: Fases de la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="a2b00-102">Fases de la migración</span><span class="sxs-lookup"><span data-stu-id="a2b00-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2b00-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="a2b00-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="a2b00-104">En Lync Server 2013, se definen sitios en la red que contienen componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2b00-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="a2b00-105">Un sitio es un conjunto de equipos que están conectados correctamente mediante una red de alta velocidad y baja latencia, como una única red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="a2b00-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="a2b00-106">Un *Grupo* de servidores front-end es un conjunto de servidores de aplicaciones para el usuario que están configurados de manera idéntica y trabajan juntos para proporcionar servicios a un grupo común de usuarios.</span><span class="sxs-lookup"><span data-stu-id="a2b00-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="a2b00-107">Un grupo proporciona capacidad de escalabilidad y conmutación por error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a2b00-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="a2b00-108">Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos.</span><span class="sxs-lookup"><span data-stu-id="a2b00-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="a2b00-109">Un servidor Standard Edition, diseñado para pequeñas organizaciones, también define un pool y se ejecuta en un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="a2b00-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="a2b00-110">Esto le permite tener la funcionalidad de Lync Server 2013 para un menor costo, pero no proporciona una verdadera solución de alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="a2b00-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="a2b00-111">Las siguientes fases describen el proceso de migración de grupo de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a2b00-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="a2b00-112">Para varios sitios que contienen varios grupos, cada grupo debe seguir este enfoque por fases.</span><span class="sxs-lookup"><span data-stu-id="a2b00-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="a2b00-113">Fase 1: planear la migración desde Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a2b00-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="a2b00-114">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="a2b00-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="a2b00-115">Fase 3: implementar el grupo de pruebas piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2b00-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="a2b00-116">Fase 4: mover los usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="a2b00-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="a2b00-117">Fase 5: agregar el servidor perimetral 2013 de Lync Server a un grupo piloto</span><span class="sxs-lookup"><span data-stu-id="a2b00-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="a2b00-118">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="a2b00-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="a2b00-119">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="a2b00-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="a2b00-120">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="a2b00-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

