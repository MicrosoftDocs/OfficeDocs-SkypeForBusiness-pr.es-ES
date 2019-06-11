---
title: Migrar Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="bf12b-102">Migrar Lync Server 2010 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf12b-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf12b-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="bf12b-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="bf12b-104">Los temas de esta sección le guiarán a través del proceso de migración de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf12b-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bf12b-105">Este documento describe los pasos que generalmente se necesitan para realizar cada fase de la migración.</span><span class="sxs-lookup"><span data-stu-id="bf12b-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="bf12b-106">No se trata de todas las topologías de implementación heredadas o de todos los escenarios posibles de migración.</span><span class="sxs-lookup"><span data-stu-id="bf12b-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="bf12b-107">Por lo tanto, es posible que no tenga que realizar cada paso descrito, o puede que tenga que realizar algunos pasos adicionales, en función de su implementación.</span><span class="sxs-lookup"><span data-stu-id="bf12b-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="bf12b-108">Este documento también proporciona ejemplos de pasos de verificación.</span><span class="sxs-lookup"><span data-stu-id="bf12b-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="bf12b-109">Estos pasos de verificación se proporcionan para ayudarle a comprender lo que debe buscar para asegurarse de que cada fase se complete correctamente a medida que avanza en la migración.</span><span class="sxs-lookup"><span data-stu-id="bf12b-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="bf12b-110">Adapte estos pasos de verificación a su proceso de migración específico.</span><span class="sxs-lookup"><span data-stu-id="bf12b-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="bf12b-111">Esta guía proporciona información específica para actualizar la implementación existente.</span><span class="sxs-lookup"><span data-stu-id="bf12b-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="bf12b-112">No se explica cómo cambiar la topología existente.</span><span class="sxs-lookup"><span data-stu-id="bf12b-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="bf12b-113">Esta guía no cubre la implementación de nuevas características.</span><span class="sxs-lookup"><span data-stu-id="bf12b-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="bf12b-114">Cuando un procedimiento detallado está documentado en otra parte, esta guía le dirige a la sección documento o documento adecuada.</span><span class="sxs-lookup"><span data-stu-id="bf12b-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="bf12b-115">Este documento define los términos según se especifican en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="bf12b-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="bf12b-116">*realizar*</span><span class="sxs-lookup"><span data-stu-id="bf12b-116">*migration*</span></span>  
    <span data-ttu-id="bf12b-117">Mover la implementación de producción de una versión anterior de Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bf12b-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="bf12b-118">*actualiza*</span><span class="sxs-lookup"><span data-stu-id="bf12b-118">*upgrade*</span></span>  
    <span data-ttu-id="bf12b-119">Instalar una versión más reciente del software en un servidor o en un equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="bf12b-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="bf12b-120">*coexistencia*</span><span class="sxs-lookup"><span data-stu-id="bf12b-120">*coexistence*</span></span>  
    <span data-ttu-id="bf12b-121">El entorno temporal que existe durante la migración cuando se ha migrado cierta funcionalidad a Lync Server 2013 y otras funciones siguen en una versión anterior de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bf12b-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="bf12b-122">*interoperabilidad*</span><span class="sxs-lookup"><span data-stu-id="bf12b-122">*interoperability*</span></span>  
    <span data-ttu-id="bf12b-123">La capacidad de la implementación para funcionar correctamente durante el período de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="bf12b-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf12b-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bf12b-124">In This Section</span></span>

  - [<span data-ttu-id="bf12b-125">Antes de comenzar la migración</span><span class="sxs-lookup"><span data-stu-id="bf12b-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="bf12b-126">Fase 1: planear la migración desde Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bf12b-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="bf12b-127">Fase 2: Preparación de la migración</span><span class="sxs-lookup"><span data-stu-id="bf12b-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="bf12b-128">Fase 3: implementar el grupo de pruebas piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf12b-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="bf12b-129">Fase 4: mover los usuarios de prueba al grupo piloto</span><span class="sxs-lookup"><span data-stu-id="bf12b-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="bf12b-130">Fase 5: agregar el servidor perimetral 2013 de Lync Server a un grupo piloto</span><span class="sxs-lookup"><span data-stu-id="bf12b-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="bf12b-131">Fase 6: Pasar de la implementación piloto a la producción</span><span class="sxs-lookup"><span data-stu-id="bf12b-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="bf12b-132">Fase 7: Finalización de las tareas posteriores a la migración</span><span class="sxs-lookup"><span data-stu-id="bf12b-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="bf12b-133">Fase 8: Retirar los grupos de servidores heredados</span><span class="sxs-lookup"><span data-stu-id="bf12b-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

