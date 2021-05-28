---
title: Administrar plantillas de equipo en el Centro de administración
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
description: Obtenga información sobre cómo administrar plantillas de equipo en el Centro de administración
ms.openlocfilehash: dd88f76d0f74b6a1fe48bd934e7cfc8ee9ab4ccc
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684587"
---
# <a name="manage-team-templates-in-the-admin-center"></a><span data-ttu-id="76bf2-103">Administrar plantillas de equipo en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="76bf2-103">Manage team templates in the admin center</span></span>

<span data-ttu-id="76bf2-104">Administre las plantillas de equipo que ven los usuarios finales creando directivas de plantillas en el Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="76bf2-104">Manage the team templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="76bf2-105">Dentro de cada directiva de plantilla, puede designar qué plantillas se muestran u ocultan.</span><span class="sxs-lookup"><span data-stu-id="76bf2-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="76bf2-106">Asigne diferentes usuarios a distintas directivas de plantilla para que los usuarios solo puedan ver el subconjunto de plantillas de equipo especificadas.</span><span class="sxs-lookup"><span data-stu-id="76bf2-106">Assign different users to different template policies so that your users view only the subset of team templates specified.</span></span>

<span data-ttu-id="76bf2-107">Vea este breve vídeo para obtener información sobre cómo administrar directivas de plantilla.</span><span class="sxs-lookup"><span data-stu-id="76bf2-107">Watch this short video to learn how to manage template policies.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="76bf2-108">Crear directivas de plantilla y asignar plantillas disponibles</span><span class="sxs-lookup"><span data-stu-id="76bf2-108">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="76bf2-109">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="76bf2-109">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="76bf2-110">Expanda **Teams**  >  **de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="76bf2-110">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="76bf2-111">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="76bf2-111">Select **Add**.</span></span>

    ![Las directivas de plantilla están seleccionadas y Agregar está resaltada](media/template-policies-1.png)

1. <span data-ttu-id="76bf2-113">En la **sección Directivas Configuración** plantillas, complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="76bf2-113">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="76bf2-114">Nombre de la directiva de plantillas</span><span class="sxs-lookup"><span data-stu-id="76bf2-114">Templates Policy name</span></span>

    - <span data-ttu-id="76bf2-115">Descripción breve de la directiva de plantillas</span><span class="sxs-lookup"><span data-stu-id="76bf2-115">Templates Policy short description</span></span>

2. <span data-ttu-id="76bf2-116">En la **tabla Plantillas visualizables,** seleccione las plantillas que desea ocultar y seleccione **Ocultar.**</span><span class="sxs-lookup"><span data-stu-id="76bf2-116">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Las plantillas seleccionadas con ocultar resaltadas](media/template-policies-2.png)

    <span data-ttu-id="76bf2-118">Puede ver las plantillas que ha seleccionado para ocultar en la **tabla Plantillas ocultas.**</span><span class="sxs-lookup"><span data-stu-id="76bf2-118">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="76bf2-119">Para mostrar determinadas plantillas, desplácese hasta la **tabla Plantillas ocultas.**</span><span class="sxs-lookup"><span data-stu-id="76bf2-119">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

2. <span data-ttu-id="76bf2-120">Seleccione las plantillas que desea mostrar y, a continuación, **seleccione Mostrar.**</span><span class="sxs-lookup"><span data-stu-id="76bf2-120">Select the templates to unhide, and then select **Show**.</span></span>

   ![Las plantillas seleccionadas que no están ocultas](media/template-policies-3.png)

   <span data-ttu-id="76bf2-122">Las plantillas seleccionadas aparecerán en la **tabla Plantillas visualizables.**</span><span class="sxs-lookup"><span data-stu-id="76bf2-122">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="76bf2-123">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="76bf2-123">Select **Save**.</span></span>

   <span data-ttu-id="76bf2-124">La nueva directiva de plantilla se muestra en la **lista Directivas de** plantillas.</span><span class="sxs-lookup"><span data-stu-id="76bf2-124">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="76bf2-125">Asignar usuarios a las directivas de plantilla</span><span class="sxs-lookup"><span data-stu-id="76bf2-125">Assign users to the template policies</span></span>

<span data-ttu-id="76bf2-126">Los usuarios asignados a una directiva solo podrán ver las plantillas que se pueden ver dentro de esa directiva.</span><span class="sxs-lookup"><span data-stu-id="76bf2-126">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="76bf2-127">En **Directivas de plantillas,** seleccione una directiva y, a continuación, **seleccione Administrar usuarios.**</span><span class="sxs-lookup"><span data-stu-id="76bf2-127">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="76bf2-128">Escriba los usuarios que desea asignar a esta directiva.</span><span class="sxs-lookup"><span data-stu-id="76bf2-128">Type the users to assign to this policy.</span></span>

   ![asignar usuarios a una directiva de plantilla](media/template-policies-4.png)

3. <span data-ttu-id="76bf2-130">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="76bf2-130">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="76bf2-131">La nueva directiva puede tardar hasta 24 horas en tener efecto para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="76bf2-131">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="76bf2-132">Límites de tamaño para directivas de plantilla</span><span class="sxs-lookup"><span data-stu-id="76bf2-132">Size limits for Template policies</span></span>

<span data-ttu-id="76bf2-133">Puede ocultar un máximo de 100 plantillas por directiva.</span><span class="sxs-lookup"><span data-stu-id="76bf2-133">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="76bf2-134">El **botón** Ocultar está deshabilitado si la directiva dada ya tiene 100 plantillas ocultas.</span><span class="sxs-lookup"><span data-stu-id="76bf2-134">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="76bf2-135">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="76bf2-135">Frequently asked questions</span></span>

<span data-ttu-id="76bf2-136">**P: ¿Puedo asignar usuarios por lotes a directivas de plantillas de equipo?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-136">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="76bf2-137">A: Sí, se admite la asignación por lotes para la directiva de plantilla en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76bf2-137">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="76bf2-138">El tipo de directiva para esta acción es TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="76bf2-138">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="76bf2-139">Aprende más</span><span class="sxs-lookup"><span data-stu-id="76bf2-139">Learn more</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

<span data-ttu-id="76bf2-140">**P: ¿Se pueden asignar grupos a directivas de plantillas de equipo?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-140">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="76bf2-141">A: Actualmente no.</span><span class="sxs-lookup"><span data-stu-id="76bf2-141">A: Currently no.</span></span> <span data-ttu-id="76bf2-142">Esta funcionalidad estará disponible en el futuro.</span><span class="sxs-lookup"><span data-stu-id="76bf2-142">This functionality will be available in the future.</span></span>

<span data-ttu-id="76bf2-143">**P: Si se crea una plantilla nueva, ¿se incluirá la plantilla en mis directivas?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-143">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="76bf2-144">A: Las plantillas nuevas estarán visibles de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="76bf2-144">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="76bf2-145">Puede elegir ocultar la plantilla en el Centro de administración en la sección Directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="76bf2-145">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="76bf2-146">**P: ¿Qué sucede si se elimina una plantilla?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-146">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="76bf2-147">A: Las plantillas eliminadas ya no estarán presentes en las directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="76bf2-147">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="76bf2-148">**P: ¿Puedo asignar varios usuarios a una directiva de plantilla en el centro de Teams administración?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-148">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="76bf2-149">A: Sí.</span><span class="sxs-lookup"><span data-stu-id="76bf2-149">A: Yes.</span></span>

1. <span data-ttu-id="76bf2-150">En el Centro de administración, vaya a **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="76bf2-150">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="76bf2-151">En la tabla de lista Usuarios, seleccione los usuarios que desea asignar a una directiva de plantillas determinada.</span><span class="sxs-lookup"><span data-stu-id="76bf2-151">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="76bf2-152">Seleccione Editar configuración y cambie el campo Directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="76bf2-152">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="76bf2-153">Seleccione Aplicar.</span><span class="sxs-lookup"><span data-stu-id="76bf2-153">Select apply.</span></span>
   <span data-ttu-id="76bf2-154">Más información [Asignar directivas a los usuarios en Microsoft Teams - Microsoft Teams Microsoft \| Docs](./assign-policies.md#assign-a-policy-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="76bf2-154">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](./assign-policies.md#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="76bf2-155">**P: ¿Cómo puedo ver todos los usuarios asignados a una directiva específica?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-155">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="76bf2-156">A: En el Centro de administración:</span><span class="sxs-lookup"><span data-stu-id="76bf2-156">A: In the Admin center:</span></span>

1. <span data-ttu-id="76bf2-157">Vaya a la **sección** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="76bf2-157">Go to the **Users** section.</span></span>
2. <span data-ttu-id="76bf2-158">Seleccione el filtro en la tabla de lista Usuarios y filtre para la directiva de plantilla de equipo.</span><span class="sxs-lookup"><span data-stu-id="76bf2-158">Select the filter in the Users list table and filter for the team template policy.</span></span>
3. <span data-ttu-id="76bf2-159">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="76bf2-159">Select **Apply**.</span></span>

![Directiva de plantilla seleccionada y ver usuarios](media/template-policies-5.png)

<span data-ttu-id="76bf2-161">**P: ¿Puedo administrar directivas de plantillas a través de PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-161">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="76bf2-162">A: No, no se admite la administración de plantillas en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76bf2-162">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="76bf2-163">**P: ¿Son aplicables las directivas de plantillas a EDU?**</span><span class="sxs-lookup"><span data-stu-id="76bf2-163">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="76bf2-164">A: No, no se admiten las directivas de plantilla para EDU.</span><span class="sxs-lookup"><span data-stu-id="76bf2-164">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="76bf2-165">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="76bf2-165">Related topics</span></span>

- [<span data-ttu-id="76bf2-166">Introducción a las plantillas de equipo en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="76bf2-166">Get started with team templates in the admin center</span></span>](./get-started-with-teams-templates-in-the-admin-console.md)

- [<span data-ttu-id="76bf2-167">Crear una plantilla de equipo personalizada</span><span class="sxs-lookup"><span data-stu-id="76bf2-167">Create a custom team template</span></span>](./create-a-team-template.md)

- [<span data-ttu-id="76bf2-168">Crear una plantilla a partir de un equipo existente</span><span class="sxs-lookup"><span data-stu-id="76bf2-168">Create a template from an existing team</span></span>](./create-template-from-existing-team.md)

- [<span data-ttu-id="76bf2-169">Crear una plantilla de equipo a partir de una plantilla de equipo existente</span><span class="sxs-lookup"><span data-stu-id="76bf2-169">Create a team template from an existing team template</span></span>](./create-template-from-existing-template.md)

- [<span data-ttu-id="76bf2-170">Asignar directivas a los usuarios en Microsoft Teams: Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="76bf2-170">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](./assign-policies.md)

- [<span data-ttu-id="76bf2-171">Asignar usuarios por lotes a una directiva</span><span class="sxs-lookup"><span data-stu-id="76bf2-171">Batch assign users to a policy</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
