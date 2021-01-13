---
title: Paquetes de directivas de Teams para administración pública
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
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización gubernamental.
ms.openlocfilehash: 19e2c692f2b5109e3ef0915ced9fd2b68c56e482
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812890"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="2cee6-103">Paquetes de directivas de Teams para administración pública</span><span class="sxs-lookup"><span data-stu-id="2cee6-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="2cee6-104">Los paquetes de directivas no están disponibles actualmente en las implementaciones de Microsoft 365 Government GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="2cee6-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="2cee6-105">Descripción general</span><span class="sxs-lookup"><span data-stu-id="2cee6-105">Overview</span></span>

<span data-ttu-id="2cee6-106">Un [paquete de directivas](manage-policy-packages.md) en Microsoft Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="2cee6-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="2cee6-107">Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="2cee6-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="2cee6-108">Puede personalizar la configuración de las directivas del paquete para adaptarla a las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2cee6-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="2cee6-109">Al cambiar la configuración de directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="2cee6-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="2cee6-110">Puede administrar paquetes de directivas mediante el Centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cee6-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="2cee6-111">Los paquetes de directiva definen previamente directivas para las siguientes, dependiendo del paquete:</span><span class="sxs-lookup"><span data-stu-id="2cee6-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="2cee6-112">Mensajería </span><span class="sxs-lookup"><span data-stu-id="2cee6-112">Messaging</span></span>
- <span data-ttu-id="2cee6-113">Reuniones</span><span class="sxs-lookup"><span data-stu-id="2cee6-113">Meetings</span></span>
- <span data-ttu-id="2cee6-114">Llamadas</span><span class="sxs-lookup"><span data-stu-id="2cee6-114">Calling</span></span>
- <span data-ttu-id="2cee6-115">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2cee6-115">App setup</span></span>
- <span data-ttu-id="2cee6-116">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="2cee6-116">Live events</span></span>

<span data-ttu-id="2cee6-117">Teams incluye actualmente los siguientes paquetes de directiva para administración pública.</span><span class="sxs-lookup"><span data-stu-id="2cee6-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="2cee6-118">Nombre del paquete en el Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2cee6-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="2cee6-119">Recomendado para</span><span class="sxs-lookup"><span data-stu-id="2cee6-119">Best used for</span></span>|<span data-ttu-id="2cee6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cee6-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2cee6-121">Responsable de seguridad pública</span><span class="sxs-lookup"><span data-stu-id="2cee6-121">Public safety officer</span></span>  |<span data-ttu-id="2cee6-122">Responsables de seguridad pública de su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="2cee6-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="2cee6-123">Crea un conjunto de directivas y configuraciones de directivas que se aplican a los responsables de seguridad pública de su organización.</span><span class="sxs-lookup"><span data-stu-id="2cee6-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="2cee6-124">Firstline Manager</span><span class="sxs-lookup"><span data-stu-id="2cee6-124">Firstline manager</span></span>  |<span data-ttu-id="2cee6-125">Administradores de primera línea de la organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="2cee6-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="2cee6-126">Crea un conjunto de directivas y aplica esa configuración a los administradores de primera línea de su organización.</span><span class="sxs-lookup"><span data-stu-id="2cee6-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="2cee6-127">Trabajador de primera línea</span><span class="sxs-lookup"><span data-stu-id="2cee6-127">Firstline worker</span></span>  |<span data-ttu-id="2cee6-128">Firstline Workers in your government organization</span><span class="sxs-lookup"><span data-stu-id="2cee6-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="2cee6-129">Crea un conjunto de directivas y aplica esa configuración a los Firstline Workers de su organización.</span><span class="sxs-lookup"><span data-stu-id="2cee6-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Captura de pantalla de paquetes de directivas sanitarias](media/policy-packages-gov.png)

<span data-ttu-id="2cee6-131">A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="2cee6-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="2cee6-132">Por ejemplo, al asignar el paquete de directiva de responsable de seguridad pública a los usuarios de la organización, se crea una directiva denominada PublicSafety_Officer para cada directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="2cee6-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Captura de pantalla de las directivas del paquete de trabajadores sanitarios](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="2cee6-134">Administrar los paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="2cee6-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="2cee6-135">Ver</span><span class="sxs-lookup"><span data-stu-id="2cee6-135">View</span></span>

<span data-ttu-id="2cee6-136">Ver la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="2cee6-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="2cee6-137">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Paquetes de directivas**, escoja el nombre del paquete y seleccione el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2cee6-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="2cee6-138">Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="2cee6-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="2cee6-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="2cee6-139">Customize</span></span>

<span data-ttu-id="2cee6-140">Personalice la configuración de las directivas en el paquete de directivas, según sea necesario, para adecuarlas a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="2cee6-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="2cee6-141">Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete.</span><span class="sxs-lookup"><span data-stu-id="2cee6-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="2cee6-142">Para editar la configuración de una directiva en un paquete de directivas, seleccione el paquete de directivas en el Centro de administración de Microsoft Teams. Luego, seleccione el nombre de la directiva que quiera editar y, finalmente, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2cee6-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="2cee6-143">Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="2cee6-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="2cee6-144">Para obtener más información, consulte [Personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="2cee6-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="2cee6-145">Asignar</span><span class="sxs-lookup"><span data-stu-id="2cee6-145">Assign</span></span>

<span data-ttu-id="2cee6-146">Asigne el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2cee6-146">Assign the policy package to users.</span></span> <span data-ttu-id="2cee6-147">Si un usuario tiene una directiva asignada y posteriormente asigna otra directiva, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="2cee6-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="2cee6-148">Asignar un paquete de directivas a uno o más usuarios</span><span class="sxs-lookup"><span data-stu-id="2cee6-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="2cee6-149">Para asignar un paquete de directivas a uno o más usuarios, vaya al panel de navegación izquierdo del Centro de administración de Microsoft Teams. Allí, seleccione **Paquetes de directivas** y, después, **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="2cee6-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Captura de pantalla que muestra cómo asignar un paquete de directivas en el Centro de administración](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="2cee6-151">Para obtener más información, consulte [Asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="2cee6-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="2cee6-152">Si un usuario tiene una directiva asignada y posteriormente asigna otra directiva, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="2cee6-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="2cee6-153">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="2cee6-153">Assign a policy package to a group</span></span>

<span data-ttu-id="2cee6-154">**Esta característica está en versión preliminar privada**</span><span class="sxs-lookup"><span data-stu-id="2cee6-154">**This feature is in private preview**</span></span>

<span data-ttu-id="2cee6-155">La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="2cee6-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="2cee6-156">La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="2cee6-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="2cee6-157">A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.</span><span class="sxs-lookup"><span data-stu-id="2cee6-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="2cee6-158">Este método es el recomendado para grupos de hasta 50 000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="2cee6-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="2cee6-159">Para obtener más información, consulte [Asignar un paquete de directivas a un grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="2cee6-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="2cee6-160">Asignar un paquete de directivas a un conjunto amplio (un lote) de usuarios</span><span class="sxs-lookup"><span data-stu-id="2cee6-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="2cee6-161">Use la asignación de paquete de directiva por lotes para asignar un paquete de directivas a grandes grupos de usuarios de una sola vez.</span><span class="sxs-lookup"><span data-stu-id="2cee6-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="2cee6-162">Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que quiera asignar.</span><span class="sxs-lookup"><span data-stu-id="2cee6-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="2cee6-163">Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="2cee6-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="2cee6-164">Un lote puede contener hasta 5000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="2cee6-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="2cee6-165">Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2cee6-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="2cee6-166">Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="2cee6-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2cee6-167">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2cee6-167">Related topics</span></span>

[<span data-ttu-id="2cee6-168">Administrar los paquetes de directivas para Teams</span><span class="sxs-lookup"><span data-stu-id="2cee6-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="2cee6-169">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="2cee6-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
