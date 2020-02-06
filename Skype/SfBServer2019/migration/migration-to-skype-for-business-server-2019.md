---
title: Migración a Skype empresarial Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Los temas de esta sección le guían a través del proceso de migración a Skype empresarial Server 2019.
ms.openlocfilehash: 51c3be10b90198e1abe24172aa35ab167e871739
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813408"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="d0f40-103">Migración a Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="d0f40-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="d0f40-104">Los temas de esta sección le guían a través del proceso de migración a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d0f40-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="d0f40-105">En este artículo se describe la migración de Lync Server 2013 o Skype empresarial 2015 a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d0f40-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0f40-106">En todo el contenido, usamos el término *heredado* para referirse a los sistemas de Lync Server 2013 o Skype empresarial Server 2015 que está migrando a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d0f40-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d0f40-107">En esta guía, se describen los pasos necesarios para llevar a cabo cada fase de la migración.</span><span class="sxs-lookup"><span data-stu-id="d0f40-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="d0f40-108">No se trata de todas las topologías de implementación heredadas o de todos los escenarios posibles de migración.</span><span class="sxs-lookup"><span data-stu-id="d0f40-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="d0f40-109">Por lo tanto, es posible que no tenga que realizar cada paso descrito, o puede que tenga que realizar algunos pasos adicionales, en función de su implementación.</span><span class="sxs-lookup"><span data-stu-id="d0f40-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="d0f40-110">Esta guía también proporciona ejemplos de pasos de verificación.</span><span class="sxs-lookup"><span data-stu-id="d0f40-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="d0f40-111">Estos pasos de verificación se proporcionan para ayudarle a comprender lo que debe buscar para asegurarse de que cada fase se complete correctamente a medida que avanza en la migración.</span><span class="sxs-lookup"><span data-stu-id="d0f40-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="d0f40-112">Adapte estos pasos de verificación a su proceso de migración específico.</span><span class="sxs-lookup"><span data-stu-id="d0f40-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="d0f40-113">Esta guía proporciona información específica para actualizar la implementación existente.</span><span class="sxs-lookup"><span data-stu-id="d0f40-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="d0f40-114">No se explica cómo cambiar la topología existente.</span><span class="sxs-lookup"><span data-stu-id="d0f40-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="d0f40-115">Esta guía no cubre la implementación de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="d0f40-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="d0f40-116">Cuando se documenta un procedimiento detallado en otra parte, esta guía le dirige a la sección de artículo o artículo.</span><span class="sxs-lookup"><span data-stu-id="d0f40-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="d0f40-117">En este artículo se definen los términos según se especifica en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="d0f40-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="d0f40-118">**migración:** Mover la implementación de producción de Lync Server 2013 o Skype empresarial 2015 a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d0f40-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="d0f40-119">**coexistencia:** El entorno temporal que existe durante la migración cuando se ha migrado cierta funcionalidad a Skype empresarial Server 2019 y otras funciones siguen en una versión anterior.</span><span class="sxs-lookup"><span data-stu-id="d0f40-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="d0f40-120">**interoperabilidad:** La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="d0f40-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="d0f40-121">**heredado:** El sistema desde el que se está migrando, que es Lync Server 2013 o Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d0f40-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="d0f40-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d0f40-122">In this section</span></span>

- [<span data-ttu-id="d0f40-123">Antes de comenzar la migración</span><span class="sxs-lookup"><span data-stu-id="d0f40-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="d0f40-124">Fase 1: Planear la migración</span><span class="sxs-lookup"><span data-stu-id="d0f40-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="d0f40-125">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="d0f40-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="d0f40-126">Fase 3: Implementar un grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="d0f40-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="d0f40-127">Fase 4: mover los usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="d0f40-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="d0f40-128">Fase 5: Agregar un servidor perimetral al grupo de servidores piloto</span><span class="sxs-lookup"><span data-stu-id="d0f40-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="d0f40-129">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="d0f40-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="d0f40-130">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="d0f40-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="d0f40-131">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="d0f40-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

