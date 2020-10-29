---
title: Paquetes de directivas de Teams para el cuidado de la salud
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización de cuidado de la salud.
ms.openlocfilehash: 6c14cc82a7e2e16780eb50c04064955aad4e4eb7
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790652"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="99995-103">Paquetes de directivas de Teams para el cuidado de la salud</span><span class="sxs-lookup"><span data-stu-id="99995-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="99995-104">Información general</span><span class="sxs-lookup"><span data-stu-id="99995-104">Overview</span></span>

<span data-ttu-id="99995-105">Un [paquete de directivas](manage-policy-packages.md) de Microsoft Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="99995-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="99995-106">Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="99995-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="99995-107">Puede personalizar la configuración de las directivas en el paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="99995-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="99995-108">Al cambiar la configuración de las directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="99995-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="99995-109">Puede administrar paquetes de directivas mediante el centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99995-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="99995-110">Los paquetes de directivas predefinen directivas para los siguientes elementos, según el paquete:</span><span class="sxs-lookup"><span data-stu-id="99995-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="99995-111">Mensajería </span><span class="sxs-lookup"><span data-stu-id="99995-111">Messaging</span></span>
- <span data-ttu-id="99995-112">Reuniones</span><span class="sxs-lookup"><span data-stu-id="99995-112">Meetings</span></span>
- <span data-ttu-id="99995-113">Llamadas</span><span class="sxs-lookup"><span data-stu-id="99995-113">Calling</span></span>
- <span data-ttu-id="99995-114">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="99995-114">App setup</span></span>
- <span data-ttu-id="99995-115">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="99995-115">Live events</span></span>

<span data-ttu-id="99995-116">Teams actualmente incluye los siguientes paquetes de política de cuidado de la salud.</span><span class="sxs-lookup"><span data-stu-id="99995-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="99995-117">Nombre del paquete en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="99995-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="99995-118">Recomendado para</span><span class="sxs-lookup"><span data-stu-id="99995-118">Best used for</span></span>|<span data-ttu-id="99995-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="99995-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="99995-120">Trabajador clínico de sanidad</span><span class="sxs-lookup"><span data-stu-id="99995-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="99995-121">Trabajadores clínicos de su organización de salud</span><span class="sxs-lookup"><span data-stu-id="99995-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="99995-122">Crea un conjunto de directivas y configuraciones de directivas que proporcionan a los trabajadores clínicos como enfermeras registradas, enfermeras, médicos y trabajadores sociales acceso completo a chats, llamadas, administración de turnos y reuniones.</span><span class="sxs-lookup"><span data-stu-id="99995-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="99995-123">Trabajador de información de asistencia sanitaria</span><span class="sxs-lookup"><span data-stu-id="99995-123">Healthcare information worker</span></span>  |<span data-ttu-id="99995-124">Trabajadores de la información en su organización de la salud</span><span class="sxs-lookup"><span data-stu-id="99995-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="99995-125">Crea un conjunto de directivas y opciones de directiva que ofrecen a trabajadores de la información como personal de ti, personal de informática, personal de finanzas y funcionarios de cumplimiento, acceso completo a chats, llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="99995-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="99995-126">Sala de pacientes sanitarios</span><span class="sxs-lookup"><span data-stu-id="99995-126">Healthcare patient room</span></span>  |<span data-ttu-id="99995-127">Dispositivos de sala de pacientes</span><span class="sxs-lookup"><span data-stu-id="99995-127">Patient room devices</span></span>|<span data-ttu-id="99995-128">Crea un conjunto de directivas y parámetros de directivas que se aplican a las salas de pacientes de su organización de salud.</span><span class="sxs-lookup"><span data-stu-id="99995-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Captura de pantalla de paquetes de política sanitaria](media/policy-packages-healthcare.png)

<span data-ttu-id="99995-130">A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="99995-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="99995-131">Por ejemplo, cuando se asigna el paquete de política de trabajadores de salud clínica a médicos de su organización, se crea una directiva llamada Healthcare_ClinicalWorker para cada Directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="99995-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Captura de pantalla de directivas en el paquete de trabajadores clínico de cuidado de la salud](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="99995-133">Introducción a los paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="99995-133">Get started with policy packages</span></span>

<span data-ttu-id="99995-134">Para empezar a usar los paquetes de directivas de asistencia sanitaria, en el Hub de incorporación del centro de administración de Microsoft, seleccione **conceptos básicos de asistencia sanitaria** y, a continuación, seleccione **asignar configuración de Directiva por rol** .</span><span class="sxs-lookup"><span data-stu-id="99995-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare basics** , and then select **Assign policy settings by role** .</span></span> <span data-ttu-id="99995-135">Una vez que esté listo para empezar, decida a qué paquetes de directivas desea asignar a las personas de su organización.</span><span class="sxs-lookup"><span data-stu-id="99995-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="99995-136">Seleccione **Ver detalles de directiva** para obtener más información sobre las directivas específicas de un paquete y su configuración correspondiente.</span><span class="sxs-lookup"><span data-stu-id="99995-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="99995-137">[Se pueden personalizar](manage-policy-packages.md#customize-policies-in-a-policy-package) después de asignarlos en el centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="99995-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="99995-138">Elija uno o varios paquetes para asignar y haga clic en **siguiente** .</span><span class="sxs-lookup"><span data-stu-id="99995-138">Choose one or multiple packages to assign and then click **Next** .</span></span> <span data-ttu-id="99995-139">Puede buscar y agregar personas al paquete de directivas que mejor se adapte a su rol.</span><span class="sxs-lookup"><span data-stu-id="99995-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="99995-140">No se puede asignar una persona a más de un paquete de directivas a la vez.</span><span class="sxs-lookup"><span data-stu-id="99995-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="99995-141">Una vez que haya agregado personas al paquete de directivas adecuado, **Finalizar** finalizará las selecciones.</span><span class="sxs-lookup"><span data-stu-id="99995-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="99995-142">Puede seguir personalizando y administrando paquetes de directivas en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="99995-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="99995-143">Administrar los paquetes de directivas </span><span class="sxs-lookup"><span data-stu-id="99995-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="99995-144">Ver</span><span class="sxs-lookup"><span data-stu-id="99995-144">View</span></span>

<span data-ttu-id="99995-145">Vea la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="99995-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="99995-146">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **paquetes de directivas** , seleccione el nombre del paquete y, a continuación, seleccione el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="99995-146">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="99995-147">Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="99995-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="99995-148">Personalizar</span><span class="sxs-lookup"><span data-stu-id="99995-148">Customize</span></span>

<span data-ttu-id="99995-149">Personalice la configuración de las directivas en el paquete de directivas según sea necesario para adaptarse a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="99995-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="99995-150">Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete.</span><span class="sxs-lookup"><span data-stu-id="99995-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="99995-151">Para editar la configuración de una directiva en un paquete de directivas, en el centro de administración de Microsoft Teams, seleccione el paquete de directivas, seleccione el nombre de la Directiva que desea editar y, después, haga clic en **Editar** .</span><span class="sxs-lookup"><span data-stu-id="99995-151">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit** .</span></span>

<span data-ttu-id="99995-152">Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="99995-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="99995-153">Para obtener más información, consulte [personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="99995-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="99995-154">Asignar</span><span class="sxs-lookup"><span data-stu-id="99995-154">Assign</span></span>

<span data-ttu-id="99995-155">Asignar el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="99995-155">Assign the policy package to users.</span></span> <span data-ttu-id="99995-156">Para asignar un paquete de directivas a uno o varios usuarios, haga clic en **administrar usuarios** .</span><span class="sxs-lookup"><span data-stu-id="99995-156">To assign a policy package to one or multiple users, click **Manage users** .</span></span> <span data-ttu-id="99995-157">También puede [usar PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para asignar un paquete de directivas a lotes grandes de usuarios.</span><span class="sxs-lookup"><span data-stu-id="99995-157">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="99995-158">Para conocer los pasos sobre cómo asignar un paquete de directivas mediante el centro de administración de Microsoft Teams o PowerShell, consulte [asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="99995-158">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Captura de pantalla de cómo asignar un paquete de directivas en el centro de administración](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="99995-160">Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="99995-160">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="99995-161">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="99995-161">Related topics</span></span>

[<span data-ttu-id="99995-162">Administrar los paquetes de directivas para Teams</span><span class="sxs-lookup"><span data-stu-id="99995-162">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="99995-163">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="99995-163">Assign policies to your users in Teams</span></span>](assign-policies.md)
