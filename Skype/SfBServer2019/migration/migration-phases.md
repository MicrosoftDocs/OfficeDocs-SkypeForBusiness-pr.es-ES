---
title: Fases de la migración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: En Skype Empresarial Server 2019, se definen los sitios de la red que contienen componentes de Skype Empresarial Server 2019. Un sitio es un conjunto de equipos que están bien conectados por una red de alta velocidad y baja latencia, como una red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752632"
---
# <a name="migration-phases"></a><span data-ttu-id="2a7fa-104">Fases de la migración</span><span class="sxs-lookup"><span data-stu-id="2a7fa-104">Migration phases</span></span>

<span data-ttu-id="2a7fa-105">En Skype Empresarial Server 2019, se definen los sitios de la red que contienen componentes de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="2a7fa-106">Un sitio es un conjunto de equipos que están bien conectados por una red de alta velocidad y baja latencia, como una red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="2a7fa-107">Un grupo de servidores front-end es un conjunto de servidores front-end configurados de manera idéntica que funcionan para ofrecer servicios para un grupo común de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="2a7fa-108">Un grupo de servidores proporciona escalabilidad y funciones de conmutación por error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="2a7fa-109">Cada servidor en un grupo debe ejecutar un rol o roles de servidores idénticos.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="2a7fa-110">Un servidor Standard Edition, diseñado para organizaciones pequeñas, también define un grupo de servidores y se ejecuta en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="2a7fa-111">Esto le permite tener la funcionalidad de Skype Empresarial Server 2019 a un menor costo, pero no proporciona una verdadera solución de alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="2a7fa-112">En las siguientes fases se describe el proceso de migración de un grupo de servidores a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="2a7fa-113">En el caso de varios sitios que contengan varios grupos, se debe seguir este enfoque por fases para cada grupo individual.</span><span class="sxs-lookup"><span data-stu-id="2a7fa-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="2a7fa-114">Fase 1: Planear la migración</span><span class="sxs-lookup"><span data-stu-id="2a7fa-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="2a7fa-115">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="2a7fa-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="2a7fa-116">Fase 3: Implementar el grupo piloto de Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="2a7fa-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="2a7fa-117">Fase 4: Mover usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="2a7fa-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="2a7fa-118">Fase 5: Agregar el servidor perimetral de Skype Empresarial Server 2019 al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="2a7fa-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="2a7fa-119">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="2a7fa-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="2a7fa-120">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="2a7fa-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="2a7fa-121">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="2a7fa-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

