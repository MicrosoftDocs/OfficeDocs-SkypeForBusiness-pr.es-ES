---
title: Administrar plantillas de Teams en el centro de administración
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
description: Obtenga información sobre cómo administrar plantillas de Teams en el centro de administración
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9704fdb92689031d44fa692383c701ec47877fc6
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145887"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="c9f5d-103">Crear y administrar plantillas de Teams en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="c9f5d-103">Create and manage Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="c9f5d-104">Administre las plantillas de Teams que se muestran a los usuarios finales creando directivas de plantillas en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-104">Manage the Teams templates that are shown to your end users by creating templates policies in the admin center.</span></span> <span data-ttu-id="c9f5d-105">Dentro de cada directiva de plantillas, puede designar qué plantillas se muestran u ocultan.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="c9f5d-106">Asigne diferentes usuarios a distintas directivas de plantillas para que los usuarios solo puedan ver el subconjunto de plantillas de Teams especificadas.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="c9f5d-107">Crear directivas de plantillas y asignar plantillas disponibles</span><span class="sxs-lookup"><span data-stu-id="c9f5d-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="c9f5d-108">Inicie sesión en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="c9f5d-109">Expanda las **directivas de plantillas**  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="c9f5d-110">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-110">Select **Add**.</span></span>

    ![Las directivas de plantilla están seleccionadas y Agregar está resaltada](media/template-policies-1.png)

1. <span data-ttu-id="c9f5d-112">En la **sección Configuración de directivas de** plantillas, complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="c9f5d-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="c9f5d-113">Nombre de la directiva de plantillas</span><span class="sxs-lookup"><span data-stu-id="c9f5d-113">Templates Policy name</span></span>

    - <span data-ttu-id="c9f5d-114">Descripción breve de la directiva de plantillas</span><span class="sxs-lookup"><span data-stu-id="c9f5d-114">Templates Policy short description</span></span>

2. <span data-ttu-id="c9f5d-115">En la **tabla Plantillas visualizables,** seleccione las plantillas que desea ocultar y seleccione **Ocultar.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Las plantillas seleccionadas con ocultar resaltado](media/template-policies-2.png)

    <span data-ttu-id="c9f5d-117">Puede ver las plantillas que ha seleccionado para ocultar en la **tabla Plantillas ocultas.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="c9f5d-118">Para mostrar determinadas plantillas, desplácese hasta la **tabla Plantillas ocultas.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="c9f5d-119">Seleccione las plantillas que desea mostrar y, a continuación, seleccione **Mostrar.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![Las plantillas seleccionadas con ocultar resaltado](media/template-policies-3.png)

   <span data-ttu-id="c9f5d-121">Las plantillas seleccionadas aparecerán en la **tabla de plantillas visualizables.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="c9f5d-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-122">Select **Save**.</span></span>

   <span data-ttu-id="c9f5d-123">La nueva directiva de plantilla se muestra en la **lista Directivas de** plantillas.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="c9f5d-124">Asignar usuarios a las directivas de plantilla</span><span class="sxs-lookup"><span data-stu-id="c9f5d-124">Assign users to the template policies</span></span>

<span data-ttu-id="c9f5d-125">Los usuarios asignados a una directiva solo podrán ver las plantillas que se pueden ver dentro de esa directiva.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="c9f5d-126">En **Directivas de plantillas,** seleccione una directiva y, a continuación, **seleccione Administrar usuarios.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="c9f5d-127">Escriba los usuarios que desea asignar a esta directiva.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-127">Type the users to assign to this policy.</span></span>

   ![Las plantillas seleccionadas con ocultar resaltado](media/template-policies-4.png)

3. <span data-ttu-id="c9f5d-129">Seleccione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="c9f5d-130">La nueva directiva puede tardar hasta 24 horas en tener efecto para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="c9f5d-131">Límites de tamaño para las directivas de plantilla</span><span class="sxs-lookup"><span data-stu-id="c9f5d-131">Size limits for Template policies</span></span>

<span data-ttu-id="c9f5d-132">Puede ocultar un máximo de 100 plantillas por directiva.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="c9f5d-133">El **botón** Ocultar está deshabilitado si la directiva determinada ya tiene ocultas 100 plantillas.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c9f5d-134">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="c9f5d-134">Frequently asked questions</span></span>

<span data-ttu-id="c9f5d-135">**P: ¿Puedo asignar usuarios por lotes a directivas de plantillas de equipo?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="c9f5d-136">A: Sí, se admite la asignación por lotes para la directiva de plantillas en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="c9f5d-137">El tipo de directiva para esta acción es TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="c9f5d-138">Aprende más</span><span class="sxs-lookup"><span data-stu-id="c9f5d-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="c9f5d-139">**P: ¿Se pueden asignar grupos a directivas de plantillas de equipo?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="c9f5d-140">A: Actualmente no.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-140">A: Currently no.</span></span> <span data-ttu-id="c9f5d-141">Esta funcionalidad estará disponible en el futuro.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="c9f5d-142">**P: Si se crea una plantilla, ¿la plantilla se incluirá en mis directivas?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="c9f5d-143">A: Las nuevas plantillas estarán visibles de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="c9f5d-144">Puede elegir ocultar la plantilla en el centro de administración en la sección Directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="c9f5d-145">**P: ¿Qué ocurre si se elimina una plantilla?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="c9f5d-146">A: Las plantillas eliminadas ya no estarán presentes en ninguna política de plantillas.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="c9f5d-147">**P: ¿Puedo asignar varios usuarios a una directiva de plantilla en el Centro de administración de Teams?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="c9f5d-148">A: Sí.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-148">A: Yes.</span></span>

1. <span data-ttu-id="c9f5d-149">En el Centro de administración, vaya a **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="c9f5d-150">En la tabla Lista de usuarios, seleccione los usuarios que desea asignar a una directiva de plantillas determinada.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="c9f5d-151">Seleccione Editar configuración y cambie el campo Directivas de plantillas.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="c9f5d-152">Seleccione Aplicar.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-152">Select apply.</span></span>
   <span data-ttu-id="c9f5d-153">Más información [sobre cómo asignar directivas a los usuarios en Microsoft Teams: Microsoft Teams \| Microsoft Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="c9f5d-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="c9f5d-154">**P: ¿Cómo puedo ver todos los usuarios asignados a una directiva específica?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="c9f5d-155">A: En el Centro de administración:</span><span class="sxs-lookup"><span data-stu-id="c9f5d-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="c9f5d-156">Vaya a la **sección** Usuarios.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="c9f5d-157">Seleccione el filtro en la tabla Lista de usuarios y filtre para la directiva de plantilla de Teams.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="c9f5d-158">Seleccione **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-158">Select **Apply**.</span></span>

![Las plantillas seleccionadas con ocultar resaltado](media/template-policies-5.png)

<span data-ttu-id="c9f5d-160">**P: ¿Puedo administrar directivas de plantillas a través de PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="c9f5d-161">A: No, esto no es compatible.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-161">A: No, this isn't supported.</span></span>

<span data-ttu-id="c9f5d-162">**P: ¿Las directivas de plantillas se aplican a EDU?**</span><span class="sxs-lookup"><span data-stu-id="c9f5d-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="c9f5d-163">A: No, esto no es compatible.</span><span class="sxs-lookup"><span data-stu-id="c9f5d-163">A: No, this isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c9f5d-164">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c9f5d-164">Related topics</span></span>

- [<span data-ttu-id="c9f5d-165">Introducción a las plantillas de equipo en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="c9f5d-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="c9f5d-166">Crear una plantilla de equipo personalizada</span><span class="sxs-lookup"><span data-stu-id="c9f5d-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="c9f5d-167">Crear una plantilla de un equipo existente</span><span class="sxs-lookup"><span data-stu-id="c9f5d-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="c9f5d-168">Crear una plantilla de equipo a partir de una plantilla de equipo existente</span><span class="sxs-lookup"><span data-stu-id="c9f5d-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="c9f5d-169">Asignar directivas a los usuarios en Microsoft Teams: Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="c9f5d-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="c9f5d-170">Asignar usuarios a una directiva por lotes</span><span class="sxs-lookup"><span data-stu-id="c9f5d-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
