---
title: Paquetes de directivas de Teams para atención sanitaria
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización sanitaria.
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812860"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="934a3-103">Paquetes de directivas de Teams para atención sanitaria</span><span class="sxs-lookup"><span data-stu-id="934a3-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="934a3-104">Información general</span><span class="sxs-lookup"><span data-stu-id="934a3-104">Overview</span></span>

<span data-ttu-id="934a3-105">Un [paquete de directivas](manage-policy-packages.md) en Microsoft Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="934a3-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="934a3-106">Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="934a3-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="934a3-107">Puede personalizar la configuración de las directivas del paquete para adaptarla a las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="934a3-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="934a3-108">Al cambiar la configuración de directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="934a3-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="934a3-109">Puede administrar paquetes de directivas mediante el Centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="934a3-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="934a3-110">Los paquetes de directiva definen previamente directivas para las siguientes, dependiendo del paquete:</span><span class="sxs-lookup"><span data-stu-id="934a3-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="934a3-111">Mensajería </span><span class="sxs-lookup"><span data-stu-id="934a3-111">Messaging</span></span>
- <span data-ttu-id="934a3-112">Reuniones</span><span class="sxs-lookup"><span data-stu-id="934a3-112">Meetings</span></span>
- <span data-ttu-id="934a3-113">Llamadas</span><span class="sxs-lookup"><span data-stu-id="934a3-113">Calling</span></span>
- <span data-ttu-id="934a3-114">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="934a3-114">App setup</span></span>
- <span data-ttu-id="934a3-115">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="934a3-115">Live events</span></span>

<span data-ttu-id="934a3-116">Teams incluye actualmente los siguientes paquetes de directivas sanitarias.</span><span class="sxs-lookup"><span data-stu-id="934a3-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="934a3-117">Nombre del paquete en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="934a3-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="934a3-118">Recomendado para</span><span class="sxs-lookup"><span data-stu-id="934a3-118">Best used for</span></span>|<span data-ttu-id="934a3-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="934a3-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="934a3-120">Trabajador sanitario</span><span class="sxs-lookup"><span data-stu-id="934a3-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="934a3-121">Trabajadores médicos de su organización sanitaria</span><span class="sxs-lookup"><span data-stu-id="934a3-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="934a3-122">Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores clínicos como enfermeras registradas, enfermeras responsables, médicos y trabajadores sociales acceso total a chat, llamadas, administración de turnos y reuniones.</span><span class="sxs-lookup"><span data-stu-id="934a3-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="934a3-123">Trabajador de la información sanitaria</span><span class="sxs-lookup"><span data-stu-id="934a3-123">Healthcare information worker</span></span>  |<span data-ttu-id="934a3-124">Trabajadores de la información de su organización sanitaria</span><span class="sxs-lookup"><span data-stu-id="934a3-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="934a3-125">Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores de la información, como el personal de IT, el personal de informática, el personal de finanzas y los responsables de cumplimiento normativo, acceso total a chats, llamadas y reuniones.</span><span class="sxs-lookup"><span data-stu-id="934a3-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="934a3-126">Sala de pacientes sanitarios</span><span class="sxs-lookup"><span data-stu-id="934a3-126">Healthcare patient room</span></span>  |<span data-ttu-id="934a3-127">Dispositivos de sala para pacientes</span><span class="sxs-lookup"><span data-stu-id="934a3-127">Patient room devices</span></span>|<span data-ttu-id="934a3-128">Crea un conjunto de directivas y configuraciones de directivas que se aplican a las salas de pacientes de su organización sanitaria.</span><span class="sxs-lookup"><span data-stu-id="934a3-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Captura de pantalla de paquetes de directivas sanitarias](media/policy-packages-healthcare.png)

<span data-ttu-id="934a3-130">A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="934a3-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="934a3-131">Por ejemplo, al asignar el paquete de directivas de trabajador médico médico a médicos de su organización, se crea una directiva denominada Healthcare_ClinicalWorker para cada directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="934a3-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Captura de pantalla de las directivas del paquete de trabajadores sanitarios](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="934a3-133">Introducción a los paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="934a3-133">Get started with policy packages</span></span>

<span data-ttu-id="934a3-134">Para empezar con los paquetes de directivas sanitarias, en el centro de integración del Centro de administración de Microsoft, seleccione Atención sanitaria y, a continuación, seleccione Asignar configuración de directiva **por rol.**</span><span class="sxs-lookup"><span data-stu-id="934a3-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="934a3-135">Cuando estés listo para empezar, decide a qué paquetes de directiva te gustaría asignar a las personas de tu organización.</span><span class="sxs-lookup"><span data-stu-id="934a3-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="934a3-136">Seleccione **Ver detalles de directiva** para obtener más información sobre las directivas específicas de un paquete y sus respectivas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="934a3-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="934a3-137">Estos [se pueden personalizar después de](manage-policy-packages.md#customize-policies-in-a-policy-package) la asignación en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="934a3-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="934a3-138">Elige uno o varios paquetes para asignar y, a continuación, haz clic **en Siguiente.**</span><span class="sxs-lookup"><span data-stu-id="934a3-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="934a3-139">Puede buscar y agregar personas al paquete de directivas más adecuado para su rol.</span><span class="sxs-lookup"><span data-stu-id="934a3-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="934a3-140">No se puede asignar a una persona más de un paquete de directiva a la vez.</span><span class="sxs-lookup"><span data-stu-id="934a3-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="934a3-141">Una vez que haya agregado personas al paquete de directiva correcto, **finalice** las selecciones.</span><span class="sxs-lookup"><span data-stu-id="934a3-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="934a3-142">Puede seguir personalizando y administrando paquetes de directivas en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="934a3-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="934a3-143">Administrar los paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="934a3-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="934a3-144">Ver</span><span class="sxs-lookup"><span data-stu-id="934a3-144">View</span></span>

<span data-ttu-id="934a3-145">Ver la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="934a3-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="934a3-146">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Paquetes de **directiva,** seleccione el nombre del paquete y, a continuación, seleccione el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="934a3-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="934a3-147">Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="934a3-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="934a3-148">Personalizar</span><span class="sxs-lookup"><span data-stu-id="934a3-148">Customize</span></span>

<span data-ttu-id="934a3-149">Personalice la configuración de las directivas en el paquete de directivas, según sea necesario, para adecuarlas a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="934a3-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="934a3-150">Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete.</span><span class="sxs-lookup"><span data-stu-id="934a3-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="934a3-151">Para editar la configuración de una directiva en un paquete de directivas, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Paquetes de **directiva,** seleccione el paquete de directiva, seleccione el nombre de la directiva que desea editar y, después, seleccione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="934a3-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="934a3-152">Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="934a3-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="934a3-153">Para obtener más información, consulte [Personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="934a3-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="934a3-154">Asignar</span><span class="sxs-lookup"><span data-stu-id="934a3-154">Assign</span></span>

<span data-ttu-id="934a3-155">Asigne el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="934a3-155">Assign the policy package to users.</span></span> <span data-ttu-id="934a3-156">Si un usuario tiene una directiva asignada y posteriormente asigna otra directiva, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="934a3-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="934a3-157">Asignar un paquete de directivas a uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="934a3-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="934a3-158">Para asignar un paquete de directivas a uno o más usuarios, vaya al panel de navegación izquierdo del Centro de administración de Microsoft Teams. Allí, seleccione **Paquetes de directivas** y, después, **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="934a3-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Captura de pantalla que muestra cómo asignar un paquete de directivas en el Centro de administración](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="934a3-160">Para obtener más información, consulte [Asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="934a3-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="934a3-161">Si un usuario tiene una directiva asignada y posteriormente asigna otra directiva, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="934a3-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="934a3-162">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="934a3-162">Assign a policy package to a group</span></span>

<span data-ttu-id="934a3-163">**Esta característica está en versión preliminar privada**</span><span class="sxs-lookup"><span data-stu-id="934a3-163">**This feature is in private preview**</span></span>

<span data-ttu-id="934a3-164">La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="934a3-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="934a3-165">La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="934a3-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="934a3-166">A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.</span><span class="sxs-lookup"><span data-stu-id="934a3-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="934a3-167">Este método es el recomendado para grupos de hasta 50 000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="934a3-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="934a3-168">Para obtener más información, consulte [Asignar un paquete de directivas a un grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="934a3-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="934a3-169">Asignar un paquete de directivas a un conjunto amplio (un lote) de usuarios</span><span class="sxs-lookup"><span data-stu-id="934a3-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="934a3-170">Use la asignación de paquete de directiva por lotes para asignar un paquete de directivas a grandes grupos de usuarios de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="934a3-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="934a3-171">Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que quiera asignar.</span><span class="sxs-lookup"><span data-stu-id="934a3-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="934a3-172">Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="934a3-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="934a3-173">Un lote puede contener hasta 5000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="934a3-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="934a3-174">Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="934a3-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="934a3-175">Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="934a3-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="934a3-176">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="934a3-176">Related topics</span></span>

[<span data-ttu-id="934a3-177">Administrar los paquetes de directivas para Teams</span><span class="sxs-lookup"><span data-stu-id="934a3-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="934a3-178">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="934a3-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
