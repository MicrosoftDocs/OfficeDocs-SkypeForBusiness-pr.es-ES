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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización de cuidado de la salud.
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578215"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="f2537-103">Paquetes de directivas de Teams para el cuidado de la salud</span><span class="sxs-lookup"><span data-stu-id="f2537-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="f2537-104">Información general</span><span class="sxs-lookup"><span data-stu-id="f2537-104">Overview</span></span>

<span data-ttu-id="f2537-105">Un [paquete de directivas](manage-policy-packages.md) de Microsoft Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="f2537-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="f2537-106">Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="f2537-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="f2537-107">Puede personalizar la configuración de las directivas en el paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2537-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="f2537-108">Al cambiar la configuración de las directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="f2537-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="f2537-109">Puede administrar paquetes de directivas mediante el centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2537-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="f2537-110">Los paquetes de directivas predefinen directivas para los siguientes elementos, según el paquete:</span><span class="sxs-lookup"><span data-stu-id="f2537-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="f2537-111">Reuniones</span><span class="sxs-lookup"><span data-stu-id="f2537-111">Meetings</span></span>
- <span data-ttu-id="f2537-112">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="f2537-112">Live events</span></span>
- <span data-ttu-id="f2537-113">Llamadas</span><span class="sxs-lookup"><span data-stu-id="f2537-113">Calling</span></span>
- <span data-ttu-id="f2537-114">Mensajería </span><span class="sxs-lookup"><span data-stu-id="f2537-114">Messaging</span></span>
- <span data-ttu-id="f2537-115">Equipos</span><span class="sxs-lookup"><span data-stu-id="f2537-115">Teams</span></span>
- <span data-ttu-id="f2537-116">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f2537-116">App setup</span></span>

<span data-ttu-id="f2537-117">Teams actualmente incluye los siguientes paquetes de política de cuidado de la salud.</span><span class="sxs-lookup"><span data-stu-id="f2537-117">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="f2537-118">Nombre del paquete en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2537-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="f2537-119">Recomendado para</span><span class="sxs-lookup"><span data-stu-id="f2537-119">Best used for</span></span>|<span data-ttu-id="f2537-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2537-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f2537-121">Trabajador clínico de sanidad</span><span class="sxs-lookup"><span data-stu-id="f2537-121">Healthcare clinical worker</span></span>  |<span data-ttu-id="f2537-122">Trabajadores clínicos de su organización de salud</span><span class="sxs-lookup"><span data-stu-id="f2537-122">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="f2537-123">Crea un conjunto de directivas y configuraciones de directivas que proporcionan a los trabajadores clínicos como enfermeras registradas, enfermeras, médicos y trabajadores sociales acceso completo a chats, llamadas, administración de turnos y reuniones.</span><span class="sxs-lookup"><span data-stu-id="f2537-123">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="f2537-124">Trabajador de información de asistencia sanitaria</span><span class="sxs-lookup"><span data-stu-id="f2537-124">Healthcare information worker</span></span>  |<span data-ttu-id="f2537-125">Trabajadores de la información en su organización de la salud</span><span class="sxs-lookup"><span data-stu-id="f2537-125">Information workers in your healthcare organization</span></span> |<span data-ttu-id="f2537-126">Crea un conjunto de directivas y opciones de directiva que ofrecen a trabajadores de la información como personal de ti, personal de informática, personal de finanzas y funcionarios de cumplimiento, acceso completo a chats, llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="f2537-126">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="f2537-127">Sala de pacientes sanitarios</span><span class="sxs-lookup"><span data-stu-id="f2537-127">Healthcare patient room</span></span>  |<span data-ttu-id="f2537-128">Dispositivos de sala de pacientes</span><span class="sxs-lookup"><span data-stu-id="f2537-128">Patient room devices</span></span>|<span data-ttu-id="f2537-129">Crea un conjunto de directivas y parámetros de directivas que se aplican a las salas de pacientes de su organización de salud.</span><span class="sxs-lookup"><span data-stu-id="f2537-129">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Captura de pantalla de paquetes de política sanitaria](media/policy-packages-healthcare.png)

<span data-ttu-id="f2537-131">A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="f2537-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="f2537-132">Por ejemplo, cuando se asigna el paquete de política de trabajadores de salud clínica a médicos de su organización, se crea una directiva llamada Healthcare_ClinicalWorker para cada Directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="f2537-132">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Captura de pantalla de directivas en el paquete de trabajadores clínico de cuidado de la salud](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="f2537-134">Administrar los paquetes de directivas </span><span class="sxs-lookup"><span data-stu-id="f2537-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="f2537-135">Ver</span><span class="sxs-lookup"><span data-stu-id="f2537-135">View</span></span>

<span data-ttu-id="f2537-136">Vea la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="f2537-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="f2537-137">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **paquetes de directivas**, seleccione el nombre del paquete y, a continuación, seleccione el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="f2537-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="f2537-138">Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2537-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="f2537-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="f2537-139">Customize</span></span>

<span data-ttu-id="f2537-140">Personalice la configuración de las directivas en el paquete de directivas según sea necesario para adaptarse a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2537-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="f2537-141">Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete.</span><span class="sxs-lookup"><span data-stu-id="f2537-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="f2537-142">Para editar la configuración de una directiva en un paquete de directivas, en el centro de administración de Microsoft Teams, seleccione el paquete de directivas, seleccione el nombre de la Directiva que desea editar y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f2537-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="f2537-143">Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="f2537-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="f2537-144">Para obtener más información, consulte [personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="f2537-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="f2537-145">Asignar</span><span class="sxs-lookup"><span data-stu-id="f2537-145">Assign</span></span>

<span data-ttu-id="f2537-146">Asignar el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2537-146">Assign the policy package to users.</span></span> <span data-ttu-id="f2537-147">Para asignar un paquete de directivas a uno o varios usuarios, haga clic en **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f2537-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="f2537-148">También puede usar PowerShell para asignar un paquete de directivas a lotes grandes de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2537-148">You can also use PowerShell to assign a policy package to large batches of users.</span></span> <span data-ttu-id="f2537-149">Para conocer los pasos sobre cómo asignar un paquete de directivas, consulte [asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="f2537-149">For steps on how to assign a policy package, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Captura de pantalla de cómo asignar un paquete de directivas en el centro de administración](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="f2537-151">Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="f2537-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2537-152">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f2537-152">Related topics</span></span>

[<span data-ttu-id="f2537-153">Administrar los paquetes de directivas para Teams</span><span class="sxs-lookup"><span data-stu-id="f2537-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="f2537-154">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="f2537-154">Assign policies to your users in Teams</span></span>](assign-policies.md)
