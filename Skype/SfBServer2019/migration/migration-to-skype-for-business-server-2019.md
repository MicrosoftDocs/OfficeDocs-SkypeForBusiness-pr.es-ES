---
title: Migración a Skype para Business Server 2019
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En los temas de esta sección le guían por el proceso de migración a Skype para Business Server 2019.
ms.openlocfilehash: 544dd01cdea68971b54374ca6e0e94909e249c82
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027833"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="3f51d-103">Migración a Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f51d-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="3f51d-104">En los temas de esta sección le guían por el proceso de migración a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3f51d-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="3f51d-105">Este artículo describen migración Lync Server 2013 o Skype para Business Server 2015 para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3f51d-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f51d-106">En todo el contenido, usamos el término de *heredado* para hacer referencia a la heredados Lync Server 2013 o Skype para Business Server 2015 que va a migrar a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3f51d-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3f51d-107">Esta guía describe los pasos que se requieren normalmente para llevar a cabo cada fase de migración.</span><span class="sxs-lookup"><span data-stu-id="3f51d-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="3f51d-108">No se trata cada topología de implementación heredada posibles o cada escenario de migración posibles.</span><span class="sxs-lookup"><span data-stu-id="3f51d-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="3f51d-109">Por lo tanto, es posible que no necesite realizar cada paso del proceso que se describen, o es posible que necesite realizar pasos adicionales, dependiendo de la implementación.</span><span class="sxs-lookup"><span data-stu-id="3f51d-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="3f51d-110">Esta guía también proporciona ejemplos de los pasos de verificación.</span><span class="sxs-lookup"><span data-stu-id="3f51d-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="3f51d-111">Se proporcionan estos pasos de comprobación que le ayudarán a comprender lo que necesita buscar para asegurarse de que cada fase se realiza correctamente a medida que avance a través de la migración.</span><span class="sxs-lookup"><span data-stu-id="3f51d-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="3f51d-112">Adaptar estos pasos de comprobación para el proceso de migración específicos.</span><span class="sxs-lookup"><span data-stu-id="3f51d-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="3f51d-113">Esta guía proporciona información específica para actualizar la implementación existente.</span><span class="sxs-lookup"><span data-stu-id="3f51d-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="3f51d-114">No se explica cómo cambiar la topología existente.</span><span class="sxs-lookup"><span data-stu-id="3f51d-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="3f51d-115">Esta guía no aborda la implementación de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="3f51d-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="3f51d-116">Cuando un procedimiento detallado está documentado en otro lugar, esta guía le dirige a la sección de artículo o el artículo.</span><span class="sxs-lookup"><span data-stu-id="3f51d-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="3f51d-117">En este artículo se define los términos tal como se especifica en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="3f51d-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="3f51d-118">**migración:** Mover la implementación de producción de Lync Server 2013 o Skype para Business Server 2015 a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3f51d-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="3f51d-119">**coexistencia:** El entorno temporal que se produce durante la migración cuando alguna funcionalidad se ha migrado a Skype para Business Server 2019 y otra funcionalidad sigue aún en una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="3f51d-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="3f51d-120">**interoperabilidad:** La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="3f51d-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="3f51d-121">**heredado:** El sistema va a migrar desde, lo que es Lync Server 2013 o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3f51d-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="3f51d-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3f51d-122">In this section</span></span>

- [<span data-ttu-id="3f51d-123">Antes de comenzar la migración</span><span class="sxs-lookup"><span data-stu-id="3f51d-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="3f51d-124">Fase 1: Planear la migración</span><span class="sxs-lookup"><span data-stu-id="3f51d-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="3f51d-125">Fase 2: Preparación para la migración</span><span class="sxs-lookup"><span data-stu-id="3f51d-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="3f51d-126">Fase 3: Implementar grupo piloto</span><span class="sxs-lookup"><span data-stu-id="3f51d-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="3f51d-127">Fase 4: Mover usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="3f51d-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="3f51d-128">Fase 5: Agregar servidor perimetral al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="3f51d-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="3f51d-129">Fase 6: Pasar de la implementación piloto a producción</span><span class="sxs-lookup"><span data-stu-id="3f51d-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="3f51d-130">Fase 7: Completar tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="3f51d-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="3f51d-131">Fase 8: Retirar grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="3f51d-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

