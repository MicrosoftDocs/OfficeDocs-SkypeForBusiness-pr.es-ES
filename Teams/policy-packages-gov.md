---
title: Teams paquetes de directivas para el gobierno
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar Teams paquetes de directivas para su organización gubernamental.
ms.openlocfilehash: 41ae937323b37948c03128efd565f40c02bbd6a2
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796874"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="ca701-103">Teams paquetes de directivas para el gobierno</span><span class="sxs-lookup"><span data-stu-id="ca701-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="ca701-104">Los paquetes de directivas no están disponibles actualmente en Microsoft 365 de administración pública GCC implementaciones de Alto o DoD.</span><span class="sxs-lookup"><span data-stu-id="ca701-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="ca701-105">Información general</span><span class="sxs-lookup"><span data-stu-id="ca701-105">Overview</span></span>

<span data-ttu-id="ca701-106">Un [paquete de directivas](manage-policy-packages.md) en Microsoft Teams es una colección de directivas y configuraciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en la organización.</span><span class="sxs-lookup"><span data-stu-id="ca701-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="ca701-107">Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="ca701-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="ca701-108">Puede personalizar la configuración de las directivas del paquete para adaptarla a las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ca701-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="ca701-109">Al cambiar la configuración de las directivas de un paquete de directiva, todos los usuarios asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="ca701-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="ca701-110">Puede administrar paquetes de directiva con el Centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca701-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="ca701-111">Los paquetes de directiva pre define directivas para las siguientes directivas, dependiendo del paquete:</span><span class="sxs-lookup"><span data-stu-id="ca701-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="ca701-112">Mensajería </span><span class="sxs-lookup"><span data-stu-id="ca701-112">Messaging</span></span>
- <span data-ttu-id="ca701-113">Reuniones</span><span class="sxs-lookup"><span data-stu-id="ca701-113">Meetings</span></span>
- <span data-ttu-id="ca701-114">Llamadas</span><span class="sxs-lookup"><span data-stu-id="ca701-114">Calling</span></span>
- <span data-ttu-id="ca701-115">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ca701-115">App setup</span></span>
- <span data-ttu-id="ca701-116">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="ca701-116">Live events</span></span>

<span data-ttu-id="ca701-117">Teams incluye actualmente los siguientes paquetes de directivas para el gobierno.</span><span class="sxs-lookup"><span data-stu-id="ca701-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="ca701-118">Nombre del paquete en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca701-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="ca701-119">Recomendado para</span><span class="sxs-lookup"><span data-stu-id="ca701-119">Best used for</span></span>|<span data-ttu-id="ca701-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca701-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ca701-121">Oficial de seguridad pública</span><span class="sxs-lookup"><span data-stu-id="ca701-121">Public safety officer</span></span>  |<span data-ttu-id="ca701-122">Agentes de seguridad pública de su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="ca701-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="ca701-123">Crea un conjunto de directivas y configuraciones de directiva que se aplican a los responsables de seguridad pública de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca701-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="ca701-124">Administrador de primera línea</span><span class="sxs-lookup"><span data-stu-id="ca701-124">Frontline manager</span></span>  |<span data-ttu-id="ca701-125">Administradores de primera línea en su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="ca701-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="ca701-126">Crea un conjunto de directivas y aplica esa configuración a los administradores de primera línea de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca701-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="ca701-127">Trabajador en primera línea</span><span class="sxs-lookup"><span data-stu-id="ca701-127">Frontline worker</span></span>  |<span data-ttu-id="ca701-128">Trabajadores de primera línea en su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="ca701-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="ca701-129">Crea un conjunto de directivas y aplica esa configuración a Los trabajadores de frontline de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca701-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![Captura de pantalla de paquetes de directivas de cuidados de la salud](media/policy-packages-gov.png)

<span data-ttu-id="ca701-131">Cada directiva individual se indica con el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="ca701-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="ca701-132">Por ejemplo, al asignar el paquete de directiva oficial de seguridad pública a los usuarios de su organización, se crea una directiva denominada PublicSafety_Officer para cada directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="ca701-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Captura de pantalla de las directivas del paquete de trabajadores clínicos sanitarios](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="ca701-134">Administrar los paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="ca701-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="ca701-135">Ver</span><span class="sxs-lookup"><span data-stu-id="ca701-135">View</span></span>

<span data-ttu-id="ca701-136">Ver la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="ca701-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="ca701-137">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Paquetes de directivas**, escoja el nombre del paquete y seleccione el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="ca701-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="ca701-138">Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca701-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="ca701-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="ca701-139">Customize</span></span>

<span data-ttu-id="ca701-140">Personalice la configuración de las directivas en el paquete de directivas, según sea necesario, para adecuarlas a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="ca701-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="ca701-141">Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete.</span><span class="sxs-lookup"><span data-stu-id="ca701-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="ca701-142">Para editar la configuración de una directiva en un paquete de directivas, seleccione el paquete de directivas en el Centro de administración de Microsoft Teams. Luego, seleccione el nombre de la directiva que quiera editar y, finalmente, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ca701-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="ca701-143">Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="ca701-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="ca701-144">Para obtener más información, consulte [Personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="ca701-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="ca701-145">Asignar</span><span class="sxs-lookup"><span data-stu-id="ca701-145">Assign</span></span>

<span data-ttu-id="ca701-p106">Asigne el paquete de directiva a los usuarios. Si un usuario tiene asignada una directiva y, después, asigna otra directiva, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="ca701-p106">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="ca701-148">Cada usuario necesitará el complemento Comunicaciones avanzadas para recibir una asignación de paquete de directiva personalizada.</span><span class="sxs-lookup"><span data-stu-id="ca701-148">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="ca701-149">Para obtener más información, vea [Complemento comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="ca701-149">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="ca701-150">Asignar un paquete de directivas a uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="ca701-150">Assign a policy package to one or several users</span></span>

<span data-ttu-id="ca701-151">Para asignar un paquete de directivas a uno o más usuarios, vaya al panel de navegación izquierdo del Centro de administración de Microsoft Teams. Allí, seleccione **Paquetes de directivas** y, después, **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ca701-151">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Captura de pantalla que muestra cómo asignar un paquete de directivas en el Centro de administración](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="ca701-153">Para obtener más información, consulte [Asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="ca701-153">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="ca701-154">Si un usuario tiene una directiva asignada y posteriormente asigna otra directiva, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="ca701-154">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="ca701-155">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="ca701-155">Assign a policy package to a group</span></span>

<span data-ttu-id="ca701-156">**Esta característica está en versión preliminar privada**</span><span class="sxs-lookup"><span data-stu-id="ca701-156">**This feature is in private preview**</span></span>

<span data-ttu-id="ca701-157">La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="ca701-157">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="ca701-158">La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="ca701-158">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="ca701-159">A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.</span><span class="sxs-lookup"><span data-stu-id="ca701-159">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="ca701-160">Este método es el recomendado para grupos de hasta 50 000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="ca701-160">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="ca701-161">Para obtener más información, consulte [Asignar un paquete de directivas a un grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="ca701-161">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="ca701-162">Asignar un paquete de directivas a un conjunto amplio (un lote) de usuarios</span><span class="sxs-lookup"><span data-stu-id="ca701-162">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="ca701-163">Use la asignación de paquete de directiva por lotes para asignar un paquete de directivas a grandes grupos de usuarios de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="ca701-163">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="ca701-164">Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que quiera asignar.</span><span class="sxs-lookup"><span data-stu-id="ca701-164">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="ca701-165">Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="ca701-165">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="ca701-166">Un lote puede contener hasta 5000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="ca701-166">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="ca701-167">Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca701-167">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="ca701-168">Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="ca701-168">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca701-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ca701-169">Related topics</span></span>

[<span data-ttu-id="ca701-170">Administrar los paquetes de directivas para Teams</span><span class="sxs-lookup"><span data-stu-id="ca701-170">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="ca701-171">Asignar paquetes de directiva a usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="ca701-171">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
