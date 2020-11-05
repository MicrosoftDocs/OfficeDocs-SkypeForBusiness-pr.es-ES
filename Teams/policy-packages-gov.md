---
title: Paquetes de directivas de Teams para administración pública
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
description: Obtenga información sobre cómo usar y administrar paquetes de directivas de Teams para su organización gubernamental.
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908599"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="58547-103">Paquetes de directivas de Teams para administración pública</span><span class="sxs-lookup"><span data-stu-id="58547-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="58547-104">Los paquetes de directivas actualmente no están disponibles en las implementaciones de Microsoft 365 gubernamentales GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="58547-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="58547-105">Información general</span><span class="sxs-lookup"><span data-stu-id="58547-105">Overview</span></span>

<span data-ttu-id="58547-106">Un [paquete de directivas](manage-policy-packages.md) de Microsoft Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="58547-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="58547-107">Los paquetes de directivas simplifican y ayudan a proporcionar consistencia al administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="58547-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="58547-108">Puede personalizar la configuración de las directivas en el paquete para satisfacer las necesidades de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="58547-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="58547-109">Al cambiar la configuración de las directivas en un paquete de directivas, todos los usuarios asignados a ese paquete obtienen la configuración actualizada.</span><span class="sxs-lookup"><span data-stu-id="58547-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="58547-110">Puede administrar paquetes de directivas mediante el centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58547-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="58547-111">Los paquetes de directivas predefinen directivas para los siguientes elementos, según el paquete:</span><span class="sxs-lookup"><span data-stu-id="58547-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="58547-112">Mensajería </span><span class="sxs-lookup"><span data-stu-id="58547-112">Messaging</span></span>
- <span data-ttu-id="58547-113">Reuniones</span><span class="sxs-lookup"><span data-stu-id="58547-113">Meetings</span></span>
- <span data-ttu-id="58547-114">Llamadas</span><span class="sxs-lookup"><span data-stu-id="58547-114">Calling</span></span>
- <span data-ttu-id="58547-115">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="58547-115">App setup</span></span>
- <span data-ttu-id="58547-116">Eventos en directo</span><span class="sxs-lookup"><span data-stu-id="58547-116">Live events</span></span>

<span data-ttu-id="58547-117">Actualmente, Teams incluye los siguientes paquetes de directivas para administración pública.</span><span class="sxs-lookup"><span data-stu-id="58547-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="58547-118">Nombre del paquete en el centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58547-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="58547-119">Recomendado para</span><span class="sxs-lookup"><span data-stu-id="58547-119">Best used for</span></span>|<span data-ttu-id="58547-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="58547-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="58547-121">Funcionario de seguridad pública</span><span class="sxs-lookup"><span data-stu-id="58547-121">Public safety officer</span></span>  |<span data-ttu-id="58547-122">Funcionarios de seguridad pública de su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="58547-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="58547-123">Crea un conjunto de directivas y parámetros de directivas que se aplican a los directores de seguridad pública de su organización.</span><span class="sxs-lookup"><span data-stu-id="58547-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="58547-124">Los Firstline Manager</span><span class="sxs-lookup"><span data-stu-id="58547-124">Firstline manager</span></span>  |<span data-ttu-id="58547-125">Los Firstline managers en su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="58547-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="58547-126">Crea un conjunto de directivas y aplica esta configuración a los administradores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="58547-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="58547-127">Trabajador de los Firstline</span><span class="sxs-lookup"><span data-stu-id="58547-127">Firstline worker</span></span>  |<span data-ttu-id="58547-128">Trabajadores de los Firstline en su organización gubernamental</span><span class="sxs-lookup"><span data-stu-id="58547-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="58547-129">Crea un conjunto de directivas y aplica esta configuración a los trabajadores de los Firstline de su organización.</span><span class="sxs-lookup"><span data-stu-id="58547-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Captura de pantalla de paquetes de política sanitaria](media/policy-packages-gov.png)

<span data-ttu-id="58547-131">A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="58547-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="58547-132">Por ejemplo, cuando se asigna el paquete de directiva del oficial de seguridad pública a los usuarios de su organización, se crea una directiva denominada PublicSafety_Officer para cada Directiva del paquete.</span><span class="sxs-lookup"><span data-stu-id="58547-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Captura de pantalla de directivas en el paquete de trabajadores clínico de cuidado de la salud](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="58547-134">Administrar los paquetes de directivas </span><span class="sxs-lookup"><span data-stu-id="58547-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="58547-135">Ver</span><span class="sxs-lookup"><span data-stu-id="58547-135">View</span></span>

<span data-ttu-id="58547-136">Vea la configuración de cada directiva en un paquete de directivas antes de asignar un paquete.</span><span class="sxs-lookup"><span data-stu-id="58547-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="58547-137">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **paquetes de directivas** , seleccione el nombre del paquete y, a continuación, seleccione el nombre de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="58547-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="58547-138">Decida si los valores predefinidos son adecuados para su organización o si necesita personalizarlos para que sean más restrictivos o flexibles según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="58547-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="58547-139">Personalizar</span><span class="sxs-lookup"><span data-stu-id="58547-139">Customize</span></span>

<span data-ttu-id="58547-140">Personalice la configuración de las directivas en el paquete de directivas según sea necesario para adaptarse a las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="58547-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="58547-141">Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete.</span><span class="sxs-lookup"><span data-stu-id="58547-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="58547-142">Para editar la configuración de una directiva en un paquete de directivas, en el centro de administración de Microsoft Teams, seleccione el paquete de directivas, seleccione el nombre de la Directiva que desea editar y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="58547-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="58547-143">Tenga en cuenta que también puede cambiar la configuración de las directivas en un paquete después de asignar el paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="58547-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="58547-144">Para obtener más información, consulte [personalizar directivas en un paquete de directivas](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="58547-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="58547-145">Asignar</span><span class="sxs-lookup"><span data-stu-id="58547-145">Assign</span></span>

<span data-ttu-id="58547-146">Asignar el paquete de directivas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="58547-146">Assign the policy package to users.</span></span> <span data-ttu-id="58547-147">Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="58547-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="58547-148">Asignar un paquete de directivas a uno o varios usuarios</span><span class="sxs-lookup"><span data-stu-id="58547-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="58547-149">Para asignar un paquete de directivas a uno o varios usuarios, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a **paquetes de directivas** y, después, seleccione **administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="58547-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![Captura de pantalla de cómo asignar un paquete de directivas en el centro de administración](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="58547-151">Para obtener más información, consulte [asignar un paquete de directivas](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="58547-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="58547-152">Si un usuario tiene asignada una directiva y posteriormente asigna otra, la asignación más reciente tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="58547-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="58547-153">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="58547-153">Assign a policy package to a group</span></span>

<span data-ttu-id="58547-154">**Esta característica está en versión preliminar privada**</span><span class="sxs-lookup"><span data-stu-id="58547-154">**This feature is in private preview**</span></span>

<span data-ttu-id="58547-155">La asignación de paquetes de directivas a grupos le permite asignar varias directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="58547-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="58547-156">La asignación de Directiva se propaga a los miembros del grupo según las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="58547-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="58547-157">A medida que se agregan o quitan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan según corresponda.</span><span class="sxs-lookup"><span data-stu-id="58547-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="58547-158">Este método se recomienda para grupos de hasta 50.000 usuarios, pero también funciona con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="58547-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="58547-159">Para obtener más información, consulte [asignar un paquete de directivas a un grupo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="58547-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="58547-160">Asignar un paquete de directivas a un conjunto grande (lote) de usuarios</span><span class="sxs-lookup"><span data-stu-id="58547-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="58547-161">Use la asignación de paquetes de directivas por lotes para asignar un paquete de directivas a grandes conjuntos de usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="58547-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="58547-162">Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="58547-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="58547-163">Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="58547-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="58547-164">Un lote puede contener hasta 5.000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="58547-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="58547-165">Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="58547-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="58547-166">Para obtener más información, consulte [asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="58547-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="58547-167">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="58547-167">Related topics</span></span>

[<span data-ttu-id="58547-168">Administrar los paquetes de directivas para Teams</span><span class="sxs-lookup"><span data-stu-id="58547-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="58547-169">Asignar directivas a los usuarios de Teams</span><span class="sxs-lookup"><span data-stu-id="58547-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
