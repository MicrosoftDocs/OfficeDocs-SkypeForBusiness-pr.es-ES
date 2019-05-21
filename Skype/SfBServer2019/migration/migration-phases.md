---
title: Fases de la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En Skype empresarial Server 2019, define sitios en su red que contienen componentes de Skype empresarial Server 2019. Un sitio es un conjunto de equipos que están conectados correctamente mediante una red de alta velocidad y baja latencia, como una única red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.
ms.openlocfilehash: 8f50f25536e330a03440702614f81c09ce74518a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298165"
---
# <a name="migration-phases"></a><span data-ttu-id="09e58-104">Fases de la migración</span><span class="sxs-lookup"><span data-stu-id="09e58-104">Migration phases</span></span>

<span data-ttu-id="09e58-105">En Skype empresarial Server 2019, define sitios en su red que contienen componentes de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="09e58-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="09e58-106">Un sitio es un conjunto de equipos que están conectados correctamente mediante una red de alta velocidad y baja latencia, como una única red de área local (LAN) o dos redes conectadas por una red de fibra óptica de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="09e58-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="09e58-107">Un grupo de servidores front-end es un conjunto de servidores de aplicaciones para el usuario que están configurados de manera idéntica y trabajan juntos para proporcionar servicios a un grupo común de usuarios.</span><span class="sxs-lookup"><span data-stu-id="09e58-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="09e58-108">Un grupo proporciona capacidad de escalabilidad y conmutación por error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="09e58-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="09e58-109">Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos.</span><span class="sxs-lookup"><span data-stu-id="09e58-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="09e58-110">Un servidor Standard Edition, diseñado para pequeñas organizaciones, también define un pool y se ejecuta en un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="09e58-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="09e58-111">Esto le permite tener la funcionalidad de Skype empresarial Server 2019 por un menor costo, pero no proporciona una verdadera solución de alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="09e58-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="09e58-112">Las siguientes fases describen el proceso de migración de grupo a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="09e58-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="09e58-113">Para varios sitios que contienen varios grupos, cada grupo debe seguir este enfoque por fases.</span><span class="sxs-lookup"><span data-stu-id="09e58-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="09e58-114">Fase 1: Planear la migración</span><span class="sxs-lookup"><span data-stu-id="09e58-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="09e58-115">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="09e58-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="09e58-116">Fase 3: implementar el grupo de pruebas piloto de Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="09e58-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="09e58-117">Fase 4: mover los usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="09e58-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="09e58-118">Fase 5: agregar el servidor perimetral de Skype empresarial Server 2019 a una agrupación piloto</span><span class="sxs-lookup"><span data-stu-id="09e58-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="09e58-119">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="09e58-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="09e58-120">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="09e58-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="09e58-121">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="09e58-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

