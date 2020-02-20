---
title: Migración de Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0688fc80bb763a4b5aa3e7ff10970cef96465b84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="460e6-102">Migración de Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="460e6-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="460e6-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="460e6-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="460e6-104">Los temas de esta sección le guiarán por el proceso de migración de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="460e6-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="460e6-p101">Este documento describe los pasos necesarios generalmente para llevar a cabo cada fase de migración. No aborda toda la topología de implementación heredada posible o cada posible escenario de migración. Por lo tanto, dependiendo de su implementación, es posible que no necesite realizar cada paso descrito o también es posible que necesite realizar pasos adicionales. Este documento también proporciona ejemplos de pasos de verificación. Estos pasos de verificación se ofrecen para ayudarle a entender lo que necesita buscar para garantizar que cada fase finalice correctamente mientras progresa a lo largo de la migración. Individualice estos pasos de verificación para su proceso de migración particular.</span><span class="sxs-lookup"><span data-stu-id="460e6-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="460e6-p102">Esta guía le ofrece información específica para actualizar su implementación existente. No explica cómo cambiar su topología existente. Tampoco aborda la implementación de nuevas características. Cuando se documenta en otro lugar un procedimiento detallado, esta guía le dirige al documento o sección del documento pertinente.</span><span class="sxs-lookup"><span data-stu-id="460e6-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="460e6-115">Este documento define términos siguiendo las especificaciones de la lista siguiente.</span><span class="sxs-lookup"><span data-stu-id="460e6-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="460e6-116">*Migraciones*</span><span class="sxs-lookup"><span data-stu-id="460e6-116">*migration*</span></span>  
    <span data-ttu-id="460e6-117">Mover la implementación de producción de una versión anterior de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="460e6-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="460e6-118">*actualización*</span><span class="sxs-lookup"><span data-stu-id="460e6-118">*upgrade*</span></span>  
    <span data-ttu-id="460e6-119">Instalar una versión de software más reciente en un equipo cliente o servidor.</span><span class="sxs-lookup"><span data-stu-id="460e6-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="460e6-120">*coexistencia*</span><span class="sxs-lookup"><span data-stu-id="460e6-120">*coexistence*</span></span>  
    <span data-ttu-id="460e6-121">El entorno temporal que existe durante la migración cuando alguna funcionalidad se ha migrado a Lync Server 2013 y la funcionalidad sigue siendo una versión anterior de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="460e6-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="460e6-122">*interoperabilidad*</span><span class="sxs-lookup"><span data-stu-id="460e6-122">*interoperability*</span></span>  
    <span data-ttu-id="460e6-123">La capacidad de su implementación para funcionar correctamente durante el período e coexistencia.</span><span class="sxs-lookup"><span data-stu-id="460e6-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="460e6-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="460e6-124">In This Section</span></span>

  - [<span data-ttu-id="460e6-125">Antes de comenzar la migración</span><span class="sxs-lookup"><span data-stu-id="460e6-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="460e6-126">Fase 1: planear la migración desde Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="460e6-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="460e6-127">Fase 2: preparar la migración</span><span class="sxs-lookup"><span data-stu-id="460e6-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="460e6-128">Fase 3: implementar el grupo piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="460e6-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="460e6-129">Fase 4: mover usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="460e6-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="460e6-130">Fase 5: agregar un servidor perimetral de Lync Server 2013 a un grupo piloto</span><span class="sxs-lookup"><span data-stu-id="460e6-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="460e6-131">Fase 6: pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="460e6-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="460e6-132">Fase 7: completar las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="460e6-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="460e6-133">Fase 8: retirar grupos heredados</span><span class="sxs-lookup"><span data-stu-id="460e6-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

