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
ms.openlocfilehash: 820cc280e7168dee5a0e059005a1b7e6cebf5ff1
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856429"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="42986-103">Asignar paquetes de directiva a usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="42986-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="42986-104">En este artículo se revisan las diferentes formas de asignar paquetes de directiva a usuarios y grupos en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="42986-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="42986-105">Antes de leer, asegúrese de que ha leído Asignar directivas [en Teams: introducción.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="42986-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="42986-106">Cada usuario necesitará el complemento de Comunicaciones avanzadas para recibir una tarea de paquete personalizado de directiva.</span><span class="sxs-lookup"><span data-stu-id="42986-106">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="42986-107">Para más información, consulte [Complemento de Comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="42986-107">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="42986-108">Asignar un paquete de directiva a los usuarios</span><span class="sxs-lookup"><span data-stu-id="42986-108">Assign a policy package to users</span></span>

<span data-ttu-id="42986-109">Un paquete de directivas en Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a usuarios que tienen los mismos roles o similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="42986-109">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="42986-110">Cada paquete de directivas está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten actividades típicas de ese rol.</span><span class="sxs-lookup"><span data-stu-id="42986-110">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="42986-111">Algunos ejemplos de paquetes de directivas son el paquete educación (profesor) y el paquete de atención sanitaria (trabajador clínico).</span><span class="sxs-lookup"><span data-stu-id="42986-111">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="42986-112">Para obtener más información, vea [Administrar paquetes de directivas en Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="42986-112">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="42986-113">Asignar un paquete de directiva a un usuario</span><span class="sxs-lookup"><span data-stu-id="42986-113">Assign a policy package to one user</span></span>

1. <span data-ttu-id="42986-114">En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Usuarios** y, a continuación, seleccione el usuario.</span><span class="sxs-lookup"><span data-stu-id="42986-114">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="42986-115">En la página del usuario, seleccione **Directivas** y, a continuación, junto **a Paquete de directivas,** seleccione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="42986-115">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="42986-116">En el **panel Asignar paquete de** directiva, seleccione el paquete que desea asignar y, a continuación, seleccione **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="42986-116">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Teams captura de pantalla del Centro de administración para la asignación de paquetes de directivas a un usuario](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="42986-118">Asignar un paquete de directiva a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="42986-118">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="42986-119">En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Paquetes de directiva y, a continuación, seleccione el paquete de directiva que desea asignar haciendo clic a la izquierda del nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="42986-119">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="42986-120">Seleccione **Administrar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="42986-120">Select **Manage users**.</span></span>
3. <span data-ttu-id="42986-121">En el panel **Administrar usuarios**, busque el usuario por su nombre para mostrar o por su nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="42986-121">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="42986-122">Repita este paso por cada usuario que quiera agregar.</span><span class="sxs-lookup"><span data-stu-id="42986-122">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="42986-123">Cuando haya terminado de agregar usuarios, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="42986-123">When you're finished adding users, select **Save**.</span></span>

![Teams captura de pantalla del Centro de administración para la asignación de paquetes de directivas a varios usuarios](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="42986-125">Asignar un paquete de directivas a un grupo</span><span class="sxs-lookup"><span data-stu-id="42986-125">Assign a policy package to a group</span></span>

<span data-ttu-id="42986-126">La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="42986-126">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="42986-127">La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad.</span><span class="sxs-lookup"><span data-stu-id="42986-127">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="42986-128">A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente.</span><span class="sxs-lookup"><span data-stu-id="42986-128">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="42986-129">La asignación de paquetes de directiva a grupos se recomienda para grupos de hasta 50 000 usuarios, pero también funcionará con grupos más grandes.</span><span class="sxs-lookup"><span data-stu-id="42986-129">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="42986-130">Al asignar el paquete de directiva, se asigna inmediatamente al grupo.</span><span class="sxs-lookup"><span data-stu-id="42986-130">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="42986-131">Sin embargo, la propagación de la asignación de directivas a los miembros del grupo se realiza como una operación en segundo plano y puede tardar algún tiempo, dependiendo del tamaño del grupo.</span><span class="sxs-lookup"><span data-stu-id="42986-131">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="42986-132">Lo mismo ocurre cuando una directiva no está desasignada de un grupo o cuando se agregan o quitan miembros de un grupo.</span><span class="sxs-lookup"><span data-stu-id="42986-132">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42986-133">Antes de empezar, es importante comprender (reglas de[prioridad)](assign-policies-users-and-groups.md#precedence-rules)y (clasificación[de asignaciones de grupo).](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="42986-133">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="42986-134">Asegúrese de leer y comprender los conceptos de ([Qué necesita saber](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)acerca de la asignación de directivas a grupos) anteriormente en este artículo.</span><span class="sxs-lookup"><span data-stu-id="42986-134">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="42986-135">Asignar un paquete de directiva a un grupo de usuarios en el centro de administración</span><span class="sxs-lookup"><span data-stu-id="42986-135">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="42986-136">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="42986-136">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="42986-137">En el panel de navegación izquierdo, vaya a la página del paquete de directivas.</span><span class="sxs-lookup"><span data-stu-id="42986-137">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="42986-138">Seleccione la pestaña Asignación de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="42986-138">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="42986-139">Seleccione **Agregar grupo** y, a continuación, en el panel Asignar un paquete de directiva al grupo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="42986-139">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="42986-140">a.</span><span class="sxs-lookup"><span data-stu-id="42986-140">a.</span></span> <span data-ttu-id="42986-141">Busque y agregue el grupo al que desea asignar el paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="42986-141">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="42986-142">b.</span><span class="sxs-lookup"><span data-stu-id="42986-142">b.</span></span> <span data-ttu-id="42986-143">Seleccione un paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="42986-143">Select a policy package.</span></span>

    <span data-ttu-id="42986-144">c.</span><span class="sxs-lookup"><span data-stu-id="42986-144">c.</span></span> <span data-ttu-id="42986-145">Establezca la clasificación para cada tipo de directiva.</span><span class="sxs-lookup"><span data-stu-id="42986-145">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="42986-146">d.</span><span class="sxs-lookup"><span data-stu-id="42986-146">d.</span></span> <span data-ttu-id="42986-147">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="42986-147">Select **Apply**.</span></span>

![muestra la asignación de directiva de grupo](media/group-pkg-assignment.png)

5. <span data-ttu-id="42986-149">Para administrar la clasificación de un tipo de directiva específico, vaya a la página de directiva específica.</span><span class="sxs-lookup"><span data-stu-id="42986-149">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="42986-150">Para reasignar un paquete de directiva a un grupo, primero quite la asignación de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="42986-150">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="42986-151">A continuación, siga los pasos anteriores para asignar el paquete de directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="42986-151">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="42986-152">Trabajar con PowerShell</span><span class="sxs-lookup"><span data-stu-id="42986-152">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="42986-153">Obtener el Teams de PowerShell</span><span class="sxs-lookup"><span data-stu-id="42986-153">Get the Teams PowerShell module</span></span>

<span data-ttu-id="42986-154">Para obtener instrucciones paso a paso, vea [Instalar Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="42986-154">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="42986-155">Asignar un paquete de directiva a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="42986-155">Assign a policy package to a group of users</span></span>

<span data-ttu-id="42986-156">Use el cmdlet [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) para asignar un paquete de directiva a un grupo.</span><span class="sxs-lookup"><span data-stu-id="42986-156">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="42986-157">Puede especificar un grupo con el id. de objeto, la dirección SIP o la dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="42986-157">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="42986-158">Al asignar el paquete de directiva, especifique una ( clasificación de asignaciones de[grupo)](assign-policies-users-and-groups.md#group-assignment-ranking)para cada tipo de directiva en el paquete de directiva.</span><span class="sxs-lookup"><span data-stu-id="42986-158">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="42986-159">En este ejemplo, asignamos el paquete de directiva de Education_Teacher a un grupo con una clasificación de asignaciones de 1 para TeamsAppSetupPolicy y TeamsMeetingBroadcastPolicy y una clasificación de 2 para TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="42986-159">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="42986-160">Asignar un paquete de directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="42986-160">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="42986-161">Con la asignación de paquetes de directivas por lotes, puede asignar un paquete de directiva a grandes conjuntos de usuarios a la vez sin tener que usar un script.</span><span class="sxs-lookup"><span data-stu-id="42986-161">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="42986-162">Use el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar un lote de usuarios y el paquete de directiva que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="42986-162">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="42986-163">Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.</span><span class="sxs-lookup"><span data-stu-id="42986-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="42986-164">A continuación, puede usar el cmdlet [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) para realizar un seguimiento del progreso y el estado de las asignaciones en un lote.</span><span class="sxs-lookup"><span data-stu-id="42986-164">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="42986-165">Especifique los usuarios por su id. de objeto o dirección del Protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="42986-165">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="42986-166">La dirección SIP de un usuario suele tener el mismo valor que el nombre principal de usuario (UPN) o la dirección de correo electrónico, pero esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="42986-166">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="42986-167">Si se especifica un usuario con su UPN o correo electrónico, pero tiene un valor diferente de su dirección SIP, la asignación de directivas no se realizará correctamente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="42986-167">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="42986-168">Si un lote incluye usuarios duplicados, los duplicados se quitarán del lote antes de procesar y el estado solo se proporciona para los usuarios únicos que permanecen en el lote.</span><span class="sxs-lookup"><span data-stu-id="42986-168">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="42986-169">Un lote contiene hasta 5 000 usuarios.</span><span class="sxs-lookup"><span data-stu-id="42986-169">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="42986-170">Para obtener los mejores resultados, no envíe más de unos pocos lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="42986-170">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="42986-171">Permitir que los lotes completen el procesamiento antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="42986-171">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="42986-172">Usar el Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="42986-172">Use the Teams PowerShell module</span></span>

<span data-ttu-id="42986-173">Ejecute lo siguiente para instalar el [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) (si aún no lo ha hecho).</span><span class="sxs-lookup"><span data-stu-id="42986-173">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="42986-174">Asegúrese de instalar la versión 1.0.5 o posterior.</span><span class="sxs-lookup"><span data-stu-id="42986-174">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="42986-175">Ejecute lo siguiente para conectarse a Teams e iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="42986-175">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="42986-176">Cuando se le solicite, inicie sesión con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="42986-176">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="42986-177">Asignar paquetes de directiva a un lote de usuarios</span><span class="sxs-lookup"><span data-stu-id="42986-177">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="42986-178">En este ejemplo, usamos el cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para asignar el paquete de directiva Education_PrimaryStudent un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="42986-178">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="42986-179">Ver el estado de una asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="42986-179">See the status of a batch assignment</span></span>

<span data-ttu-id="42986-180">Ejecute lo siguiente para obtener el estado de una asignación por lotes, donde OperationId es el id. de operación devuelto por el ```New-CsBatchPolicyAssignmentOperation``` cmdlet para un lote determinado.</span><span class="sxs-lookup"><span data-stu-id="42986-180">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="42986-181">Si el resultado muestra que se ha producido un error, ejecute lo siguiente para obtener más información sobre los errores, que se encuentran en la ```UserState``` propiedad.</span><span class="sxs-lookup"><span data-stu-id="42986-181">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="42986-182">Para obtener más información, [vea Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="42986-182">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="42986-183">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="42986-183">Related topics</span></span>

- [<span data-ttu-id="42986-184">Administrar Teams con directivas</span><span class="sxs-lookup"><span data-stu-id="42986-184">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="42986-185">Administrar paquetes de directivas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42986-185">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="42986-186">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="42986-186">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="42986-187">Asignar directivas en Teams: introducción</span><span class="sxs-lookup"><span data-stu-id="42986-187">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
