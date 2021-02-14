---
title: Migración a Skype Empresarial Server 2019
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
description: Los temas de esta sección le guiarán por el proceso de migración a Skype Empresarial Server 2019.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752622"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="6827d-103">Migración a Skype Empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="6827d-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="6827d-104">Los temas de esta sección le guiarán por el proceso de migración a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6827d-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="6827d-105">En este artículo se describe la migración de Lync Server 2013 o Skype Empresarial Server 2015 a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6827d-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6827d-106">En todo el contenido,  usamos el término heredado para hacer referencia a Lync Server 2013 heredado o Skype Empresarial Server 2015 que va a migrar a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6827d-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6827d-107">En esta guía se describen los pasos generalmente necesarios para realizar cada fase de migración.</span><span class="sxs-lookup"><span data-stu-id="6827d-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="6827d-108">No aborda toda la topología de implementación heredada posible o cada posible escenario de migración.</span><span class="sxs-lookup"><span data-stu-id="6827d-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="6827d-109">Por lo tanto, dependiendo de su implementación, es posible que no necesite realizar cada paso descrito o también es posible que necesite realizar pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="6827d-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="6827d-110">Esta guía también proporciona ejemplos de pasos de comprobación.</span><span class="sxs-lookup"><span data-stu-id="6827d-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="6827d-111">Estos pasos de verificación se ofrecen para ayudarle a entender lo que necesita buscar para garantizar que cada fase finalice correctamente mientras progresa a lo largo de la migración.</span><span class="sxs-lookup"><span data-stu-id="6827d-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="6827d-112">Individualice estos pasos de verificación para su proceso de migración particular.</span><span class="sxs-lookup"><span data-stu-id="6827d-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="6827d-113">Esta guía le ofrece información específica para actualizar su implementación existente.</span><span class="sxs-lookup"><span data-stu-id="6827d-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="6827d-114">No explica cómo cambiar su topología existente.</span><span class="sxs-lookup"><span data-stu-id="6827d-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="6827d-115">Tampoco aborda la implementación de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="6827d-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="6827d-116">Cuando se documenta un procedimiento detallado en otro lugar, esta guía le dirige a la sección de artículo o artículo.</span><span class="sxs-lookup"><span data-stu-id="6827d-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="6827d-117">En este artículo se definen los términos especificados en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="6827d-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="6827d-118">**migración:** Mover la implementación de producción de Lync Server 2013 o Skype Empresarial Server 2015 a Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6827d-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="6827d-119">**coexistencia:** El entorno temporal que existe durante la migración cuando algunas funciones se han migrado a Skype Empresarial Server 2019 y otras permanecen en una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="6827d-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="6827d-120">**interoperabilidad:** La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="6827d-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="6827d-121">**heredado:** El sistema desde el que va a migrar, que es Lync Server 2013 o Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6827d-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="6827d-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6827d-122">In this section</span></span>

- [<span data-ttu-id="6827d-123">Antes de comenzar la migración</span><span class="sxs-lookup"><span data-stu-id="6827d-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="6827d-124">Fase 1: Planear la migración</span><span class="sxs-lookup"><span data-stu-id="6827d-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="6827d-125">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="6827d-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="6827d-126">Fase 3: Implementar un grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="6827d-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="6827d-127">Fase 4: Mover usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="6827d-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="6827d-128">Fase 5: Agregar un servidor perimetral al grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="6827d-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="6827d-129">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="6827d-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="6827d-130">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="6827d-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="6827d-131">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="6827d-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

