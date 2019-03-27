---
title: Fases de la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En Skype para Business Server 2019, es posible definir sitios en la red que contienen Skype para los componentes de Business Server 2019. Un sitio es un conjunto de equipos que están bien conectados mediante una red de alta velocidad, baja latencia, como una única red de área local (LAN) o dos redes conectadas mediante una red óptica de fibra de alta velocidad.
ms.openlocfilehash: d34351b551262450dee852efd7679f17cbe1e161
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886543"
---
# <a name="migration-phases"></a><span data-ttu-id="c3014-104">Fases de la migración</span><span class="sxs-lookup"><span data-stu-id="c3014-104">Migration phases</span></span>

<span data-ttu-id="c3014-105">En Skype para Business Server 2019, es posible definir sitios en la red que contienen Skype para los componentes de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3014-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="c3014-106">Un sitio es un conjunto de equipos que están bien conectados mediante una red de alta velocidad, baja latencia, como una única red de área local (LAN) o dos redes conectadas mediante una red óptica de fibra de alta velocidad.</span><span class="sxs-lookup"><span data-stu-id="c3014-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="c3014-107">Un grupo de servidores Front-End es un conjunto de servidores Front-End que están configurados de manera idéntica y trabajo de conjuntamente para proporcionar servicios para un grupo de usuarios comunes.</span><span class="sxs-lookup"><span data-stu-id="c3014-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="c3014-108">Un grupo de servidores proporciona escalabilidad y capacidad de conmutación por error a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c3014-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="c3014-109">Todos los servidores de un grupo de servidores necesitan ejecutar uno o varios roles del servidor idénticos.</span><span class="sxs-lookup"><span data-stu-id="c3014-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="c3014-110">Un servidor Standard Edition, diseñado para las organizaciones pequeñas, también define un grupo de servidores y se ejecuta en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="c3014-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="c3014-111">Esto permite disponer de Skype para la funcionalidad de Business Server 2019 para un costo menor, pero no proporciona una solución de alta disponibilidad es true.</span><span class="sxs-lookup"><span data-stu-id="c3014-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="c3014-112">Las siguientes fases describen el proceso de una migración de grupo de servidores a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3014-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="c3014-113">Para varios sitios que contiene varios grupos de servidores, cada grupo de servidores individual debe seguir este enfoque por fases.</span><span class="sxs-lookup"><span data-stu-id="c3014-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="c3014-114">Fase 1: Planear la migración</span><span class="sxs-lookup"><span data-stu-id="c3014-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="c3014-115">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="c3014-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="c3014-116">Fase 3: Implementar Skype para Business Server 2019 el grupo piloto</span><span class="sxs-lookup"><span data-stu-id="c3014-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="c3014-117">Fase 4: Mover usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="c3014-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="c3014-118">Fase 5: Agregar Skype para servidor perimetral de Business Server 2019 al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="c3014-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="c3014-119">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="c3014-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="c3014-120">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="c3014-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="c3014-121">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="c3014-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

