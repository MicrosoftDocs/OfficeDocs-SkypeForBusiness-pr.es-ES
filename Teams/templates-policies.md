---
title: Administrar plantillas de Teams en el Centro de administración
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo administrar plantillas de Teams en el Centro de administración
ms.openlocfilehash: df734d175d521b5be3ef81bf9dd8a95d749812e2
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569016"
---
# <a name="manage-team-templates-in-the-admin-center"></a><span data-ttu-id="3b276-103">Administrar plantillas de equipo en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="3b276-103">Manage team templates in the admin center</span></span>

<span data-ttu-id="3b276-104">Administre las plantillas de Teams que ven los usuarios finales creando directivas de plantillas en el Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="3b276-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="3b276-105">Dentro de cada directiva de plantilla, puede designar qué plantillas se muestran u ocultan.</span><span class="sxs-lookup"><span data-stu-id="3b276-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="3b276-106">Asigne diferentes usuarios a distintas directivas de plantilla para que los usuarios solo puedan ver el subconjunto de plantillas de Teams especificadas.</span><span class="sxs-lookup"><span data-stu-id="3b276-106">Assign different users to different template policies so that your users view only the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="3b276-107">Crear directivas de plantilla y asignar plantillas disponibles</span><span class="sxs-lookup"><span data-stu-id="3b276-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="3b276-108">Inicie sesión en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="3b276-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="3b276-109">Expandir **directivas de plantillas** de Teams  >  .</span><span class="sxs-lookup"><span data-stu-id="3b276-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="3b276-110">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3b276-110">Select **Add**.</span></span>

    ![Las directivas de plantilla están seleccionadas y Agregar está resaltada](media/template-policies-1.png)

1. <span data-ttu-id="3b276-112">En la **sección Configuración de directivas de** plantillas, complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="3b276-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="3b276-113">Nombre de la directiva de plantillas</span><span class="sxs-lookup"><span data-stu-id="3b276-113">Templates Policy name</span></span>

    - <span data-ttu-id="3b276-114">Descripción breve de la directiva de plantillas</span><span class="sxs-lookup"><span data-stu-id="3b276-114">Templates Policy short description</span></span>

2. <span data-ttu-id="3b276-115">En la **tabla Plantillas visualizables,** seleccione las plantillas que desea ocultar y seleccione **Ocultar.**</span><span class="sxs-lookup"><span data-stu-id="3b276-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Las plantillas seleccionadas con ocultar resaltadas](media/template-policies-2.png)

    <span data-ttu-id="3b276-117">Puede ver las plantillas que ha seleccionado para ocultar en la **tabla Plantillas ocultas.**</span><span class="sxs-lookup"><span data-stu-id="3b276-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="3b276-118">Para mostrar determinadas plantillas, desplácese hasta la **tabla Plantillas ocultas.**</span><span class="sxs-lookup"><span data-stu-id="3b276-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="3b276-119">Seleccione las plantillas que desea mostrar y, a continuación, **seleccione Mostrar.**</span><span class="sxs-lookup"><span data-stu-id="3b276-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![Las plantillas seleccionadas que no están ocultas](media/template-policies-3.png)

   <span data-ttu-id="3b276-121">Las plantillas seleccionadas aparecerán en la **tabla Plantillas visualizables.**</span><span class="sxs-lookup"><span data-stu-id="3b276-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="3b276-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3b276-122">Select **Save**.</span></span>

   <span data-ttu-id="3b276-123">La nueva directiva de plantilla se muestra en la **lista Directivas de** plantillas.</span><span class="sxs-lookup"><span data-stu-id="3b276-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="3b276-124">Asignar usuarios a las directivas de plantilla</span><span class="sxs-lookup"><span data-stu-id="3b276-124">Assign users to the template policies</span></span>

<span data-ttu-id="3b276-125">Los usuarios asignados a una directiva solo podrán ver las plantillas que se pueden ver dentro de esa directiva.</span><span class="sxs-lookup"><span data-stu-id="3b276-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="3b276-126">En **Directivas de plantillas,** seleccione una directiva y, a continuación, **seleccione Administrar usuarios.**</span><span class="sxs-lookup"><span data-stu-id="3b276-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="3b276-127">Escriba los usuarios que desea asignar a esta directiva.</span><span class="sxs-lookup"><span data-stu-id="3b276-127">Type the users to assign to this policy.</span></span>

   ![asignar usuarios a una directiva de plantilla](media/template-policies-4.png)

3. <span data-ttu-id="3b276-129">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3b276-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="3b276-130">La nueva directiva puede tardar hasta 24 horas en tener efecto para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="3b276-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="3b276-131">Límites de tamaño para directivas de plantilla</span><span class="sxs-lookup"><span data-stu-id="3b276-131">Size limits for Template policies</span></span>

<span data-ttu-id="3b276-132">Puede ocultar un máximo de 100 plantillas por directiva.</span><span class="sxs-lookup"><span data-stu-id="3b276-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="3b276-133">El **botón** Ocultar está deshabilitado si la directiva dada ya tiene 100 plantillas ocultas.</span><span class="sxs-lookup"><span data-stu-id="3b276-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3b276-134">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="3b276-134">Frequently asked questions</span></span>

<span data-ttu-id="3b276-135">**P: ¿Puedo asignar usuarios por lotes a directivas de plantillas de equipo?**</span><span class="sxs-lookup"><span data-stu-id="3b276-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="3b276-136">A: Sí, se admite la asignación por lotes para la directiva de plantilla en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b276-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="3b276-137">El tipo de directiva para esta acción es TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="3b276-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="3b276-138">Aprende más</span><span class="sxs-lookup"><span data-stu-id="3b276-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="3b276-139">**P: ¿Se pueden asignar grupos a directivas de plantillas de equipo?**</span><span class="sxs-lookup"><span data-stu-id="3b276-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="3b276-140">A: Actualmente no.</span><span class="sxs-lookup"><span data-stu-id="3b276-140">A: Currently no.</span></span> <span data-ttu-id="3b276-141">Esta funcionalidad estará disponible en el futuro.</span><span class="sxs-lookup"><span data-stu-id="3b276-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="3b276-142">**P: Si se crea una plantilla nueva, ¿se incluirá la plantilla en mis directivas?**</span><span class="sxs-lookup"><span data-stu-id="3b276-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="3b276-143">A: Las plantillas nuevas estarán visibles de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3b276-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="3b276-144">Puede elegir ocultar la plantilla en el Centro de administración en la sección Directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="3b276-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="3b276-145">**P: ¿Qué sucede si se elimina una plantilla?**</span><span class="sxs-lookup"><span data-stu-id="3b276-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="3b276-146">A: Las plantillas eliminadas ya no estarán presentes en las directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="3b276-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="3b276-147">**P: ¿Puedo asignar varios usuarios a una directiva de plantilla en el Centro de administración de Teams?**</span><span class="sxs-lookup"><span data-stu-id="3b276-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="3b276-148">A: Sí.</span><span class="sxs-lookup"><span data-stu-id="3b276-148">A: Yes.</span></span>

1. <span data-ttu-id="3b276-149">En el Centro de administración, vaya a **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="3b276-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="3b276-150">En la tabla de lista Usuarios, seleccione los usuarios que desea asignar a una directiva de plantillas determinada.</span><span class="sxs-lookup"><span data-stu-id="3b276-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="3b276-151">Seleccione Editar configuración y cambie el campo Directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="3b276-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="3b276-152">Seleccione Aplicar.</span><span class="sxs-lookup"><span data-stu-id="3b276-152">Select apply.</span></span>
   <span data-ttu-id="3b276-153">Más información [Asignar directivas a los usuarios en Microsoft Teams : Microsoft Teams Microsoft \| Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="3b276-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="3b276-154">**P: ¿Cómo puedo ver todos los usuarios asignados a una directiva específica?**</span><span class="sxs-lookup"><span data-stu-id="3b276-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="3b276-155">A: En el Centro de administración:</span><span class="sxs-lookup"><span data-stu-id="3b276-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="3b276-156">Vaya a la **sección** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b276-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="3b276-157">Seleccione el filtro en la tabla de lista Usuarios y filtre para la directiva de plantilla de teams.</span><span class="sxs-lookup"><span data-stu-id="3b276-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="3b276-158">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3b276-158">Select **Apply**.</span></span>

![Directiva de plantilla seleccionada y ver usuarios](media/template-policies-5.png)

<span data-ttu-id="3b276-160">**P: ¿Puedo administrar directivas de plantillas a través de PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="3b276-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="3b276-161">A: No, no se admite la administración de plantillas en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b276-161">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="3b276-162">**P: ¿Son aplicables las directivas de plantillas a EDU?**</span><span class="sxs-lookup"><span data-stu-id="3b276-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="3b276-163">A: No, no se admiten las directivas de plantilla para EDU.</span><span class="sxs-lookup"><span data-stu-id="3b276-163">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b276-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3b276-164">Related topics</span></span>

- [<span data-ttu-id="3b276-165">Introducción a las plantillas de equipo en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="3b276-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="3b276-166">Crear una plantilla de equipo personalizada</span><span class="sxs-lookup"><span data-stu-id="3b276-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="3b276-167">Crear una plantilla a partir de un equipo existente</span><span class="sxs-lookup"><span data-stu-id="3b276-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="3b276-168">Crear una plantilla de equipo a partir de una plantilla de equipo existente</span><span class="sxs-lookup"><span data-stu-id="3b276-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="3b276-169">Asignar directivas a los usuarios en Microsoft Teams: Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="3b276-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="3b276-170">Asignar usuarios por lotes a una directiva</span><span class="sxs-lookup"><span data-stu-id="3b276-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
