---
title: Asignar paquetes de directiva a usuarios y grupos
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre las diferentes formas de asignar paquetes de directiva a usuarios y grupos en Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574351"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="36386-103">Asignar paquetes de directiva a usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="36386-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="36386-104">En este artículo se revisan las diferentes formas de asignar paquetes de directiva a usuarios y grupos en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36386-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="36386-105">Antes de leer, asegúrese de que ha leído Asignar [directivas en Teams: introducción.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="36386-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="36386-106">Asignar un paquete de directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="36386-106">Assign a policy package to users</span></span>

<span data-ttu-id="36386-107">Un paquete de directivas en Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen los mismos roles o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="36386-107">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="36386-108">Cada paquete de directivas está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="36386-108">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="36386-109">Algunos ejemplos de paquetes de directivas son el paquete educación (profesor) y el paquete de atención sanitaria (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="36386-109">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="36386-110">Para obtener más información, vea [Administrar paquetes de directivas en Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="36386-110">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="36386-111">Asignar un paquete de directiva a un usuario</span><span class="sxs-lookup"><span data-stu-id="36386-111">Assign a policy package to one user</span></span>

1. <span data-ttu-id="36386-112">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, a continuación, seleccione el usuario.</span><span class="sxs-lookup"><span data-stu-id="36386-112">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="36386-113">En la página del usuario, seleccione **Directivas** y, a continuación, junto **a Paquete de directivas,** seleccione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="36386-113">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="36386-114">En el **panel Asignar paquete de** directiva, seleccione el paquete que desea asignar y, a continuación, seleccione **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="36386-114">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Captura de pantalla del Centro de administración de Teams para la asignación de paquetes de directivas a un usuario](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="36386-116">Asignar un paquete de directiva a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="36386-116">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="36386-117">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Paquetes de directiva y, a continuación, seleccione el paquete de directiva que desea asignar haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="36386-117">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="36386-118">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="36386-118">Select **Manage users**.</span></span>
3. <span data-ttu-id="36386-119">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="36386-119">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="36386-120">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="36386-120">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="36386-121">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="36386-121">When you're finished adding users, select **Save**.</span></span>

![Captura de pantalla del Centro de administración de Teams para la asignación de paquetes de directivas a varios usuarios](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="36386-123">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="36386-123">Assign a policy package to a group</span></span>

<span data-ttu-id="36386-124">La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="36386-124">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="36386-125">La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="36386-125">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="36386-126">A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.</span><span class="sxs-lookup"><span data-stu-id="36386-126">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="36386-127">La asignación de paquetes de directiva a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="36386-127">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="36386-128">Al asignar el paquete de directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="36386-128">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="36386-129">Sin embargo, la propagación de la asignación de directivas a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="36386-129">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="36386-130">Lo mismo ocurre cuando una directiva no está desasignada de un grupo o cuando se agregan o quitan miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="36386-130">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36386-131">Antes de empezar, es importante comprender (reglas de[prioridad)](assign-policies-users-and-groups.md#precedence-rules)y (clasificación[de asignaciones de grupo).](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="36386-131">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="36386-132">Asegúrese de leer y comprender los conceptos de ([Qué necesita saber](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)acerca de la asignación de directivas a grupos) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="36386-132">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="36386-133">Asignar un paquete de directiva a un grupo de usuarios en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="36386-133">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="36386-134">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="36386-134">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="36386-135">En el panel de navegación izquierdo, vaya a la página del paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="36386-135">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="36386-136">Seleccione la pestaña Asignación de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="36386-136">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="36386-137">Seleccione **Agregar grupo** y, a continuación, en el panel Asignar un paquete de directiva al grupo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="36386-137">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="36386-138">a.</span><span class="sxs-lookup"><span data-stu-id="36386-138">a.</span></span> <span data-ttu-id="36386-139">Busque y agregue el grupo al que desea asignar el paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="36386-139">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="36386-140">b.</span><span class="sxs-lookup"><span data-stu-id="36386-140">b.</span></span> <span data-ttu-id="36386-141">Seleccione un paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="36386-141">Select a policy package.</span></span>

    <span data-ttu-id="36386-142">c.</span><span class="sxs-lookup"><span data-stu-id="36386-142">c.</span></span> <span data-ttu-id="36386-143">Establezca la clasificación para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="36386-143">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="36386-144">d.</span><span class="sxs-lookup"><span data-stu-id="36386-144">d.</span></span> <span data-ttu-id="36386-145">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="36386-145">Select **Apply**.</span></span>

![muestra la asignación de directiva de grupo](media/group-pkg-assignment.png)

5. <span data-ttu-id="36386-147">Para administrar la clasificación de un tipo de directiva específico, vaya a la página de directiva específica.</span><span class="sxs-lookup"><span data-stu-id="36386-147">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="36386-148">Para reasignar un paquete de directiva a un grupo, primero quite la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="36386-148">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="36386-149">A continuación, siga los pasos anteriores para asignar el paquete de directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36386-149">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="36386-150">Trabajar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="36386-150">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="36386-151">Obtener el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="36386-151">Get the Teams PowerShell module</span></span>

<span data-ttu-id="36386-152">Para obtener instrucciones paso a paso, vea [Instalar PowerShell de Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="36386-152">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="36386-153">Asignar un paquete de directiva a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="36386-153">Assign a policy package to a group of users</span></span>

<span data-ttu-id="36386-154">Use el cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) para asignar un paquete de directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="36386-154">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="36386-155">Puede especificar un grupo con el id. de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="36386-155">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="36386-156">Al asignar el paquete de directiva, especifique una ( clasificación de asignaciones de[grupo)](assign-policies-users-and-groups.md#group-assignment-ranking)para cada tipo de directiva en el paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="36386-156">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="36386-157">En este ejemplo, asignamos el paquete de directiva de Education_Teacher a un grupo con una clasificación de asignaciones de 1 para TeamsAppSetupPolicy y TeamsMeetingBroadcastPolicy y una clasificación de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="36386-157">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="36386-158">Asignar un paquete de directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="36386-158">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="36386-159">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="36386-159">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="36386-160">Use el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y el paquete de directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="36386-160">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="36386-161">Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="36386-161">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="36386-162">A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.</span><span class="sxs-lookup"><span data-stu-id="36386-162">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="36386-163">Especifique los usuarios por su id. de objeto o dirección del Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="36386-163">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="36386-164">La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="36386-164">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="36386-165">Si se especifica un usuario con su UPN o correo electrónico, pero tiene un valor diferente de su dirección SIP, la asignación de directivas no se realizará correctamente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="36386-165">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="36386-166">Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.</span><span class="sxs-lookup"><span data-stu-id="36386-166">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="36386-167">Un lote contiene hasta 5 000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="36386-167">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="36386-168">Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="36386-168">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="36386-169">Permitir que los lotes completen el procesamiento antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="36386-169">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="36386-170">Usar el módulo de PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="36386-170">Use the Teams PowerShell module</span></span>

<span data-ttu-id="36386-171">Ejecute lo siguiente para instalar el módulo [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) de Microsoft Teams (si aún no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="36386-171">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="36386-172">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="36386-172">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="36386-173">Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="36386-173">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="36386-174">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="36386-174">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="36386-175">Asignar paquetes de directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="36386-175">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="36386-176">En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar el paquete de directiva Education_PrimaryStudent un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="36386-176">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="36386-177">Ver el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="36386-177">See the status of a batch assignment</span></span>

<span data-ttu-id="36386-178">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el id. de operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="36386-178">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="36386-179">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que se encuentran en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="36386-179">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="36386-180">Para obtener más información, [vea Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="36386-180">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="36386-181">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="36386-181">Related topics</span></span>

- [<span data-ttu-id="36386-182">Administrar Teams con directivas</span><span class="sxs-lookup"><span data-stu-id="36386-182">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="36386-183">Administrar paquetes de directivas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36386-183">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="36386-184">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="36386-184">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="36386-185">Asignar directivas en Teams: introducción</span><span class="sxs-lookup"><span data-stu-id="36386-185">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)