---
title: Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Obtenga información sobre cómo quitar la directiva RestrictedAnonymousAccess Teams reunión de los usuarios de su organización.
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121348"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="29916-103">Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess</span><span class="sxs-lookup"><span data-stu-id="29916-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="29916-104">[Las directivas de](meeting-policies-in-teams.md) Microsoft Teams se usan para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="29916-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="29916-105">Teams incluye una directiva integrada denominada RestrictedAnonymousAccess, que contiene configuraciones predefinidas que incluyen restringir el inicio de una reunión a usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="29916-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="29916-106">(Los usuarios anónimos son usuarios que no se han autenticado). Los administradores no pueden modificar ni cambiar la configuración predefinida de la directiva de reunión.</span><span class="sxs-lookup"><span data-stu-id="29916-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="29916-107">En este artículo se muestra cómo usar PowerShell para quitar la directiva de reunión RestrictedAnonymousAccess de los usuarios a los que se les ha asignado esta directiva.</span><span class="sxs-lookup"><span data-stu-id="29916-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="29916-108">Para obtener más información sobre cómo administrar Teams con PowerShell, vea [Teams información general de PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="29916-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="29916-109">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="29916-109">Before you start</span></span>

<span data-ttu-id="29916-110">Instale y conéctese al [módulo Skype Empresarial PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="29916-110">Install and connect to the [Skype for Business PowerShell module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span> <span data-ttu-id="29916-111">Para obtener instrucciones paso a paso, vea [Instalar Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="29916-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="29916-112">Obtener las Teams directivas de reunión de su organización</span><span class="sxs-lookup"><span data-stu-id="29916-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="29916-113">Ejecute lo siguiente para obtener las Teams directivas de reunión de su organización.</span><span class="sxs-lookup"><span data-stu-id="29916-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="29916-114">En este ejemplo, se devuelve el siguiente resultado, que muestra que a dos usuarios se les asigna la directiva de reunión RestrictedAnonymousAccess.</span><span class="sxs-lookup"><span data-stu-id="29916-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="29916-115">Unassign the RestrictedAnonymous meeting policy from users</span><span class="sxs-lookup"><span data-stu-id="29916-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="29916-116">Para quitar la directiva de reunión RestrictedAnonymous de los usuarios, puede usar el cmdlet [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) si tiene un número reducido de usuarios (por ejemplo, menos de 100 usuarios).</span><span class="sxs-lookup"><span data-stu-id="29916-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="29916-117">Si tiene un gran número de usuarios (por ejemplo, más de 100 usuarios), es más eficaz usar el cmdlet  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) para enviar una operación por lotes.</span><span class="sxs-lookup"><span data-stu-id="29916-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="29916-118">Usar el cmdlet Grant-CsTeamsMeeting directiva</span><span class="sxs-lookup"><span data-stu-id="29916-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="29916-119">Ejecute lo siguiente para quitar la directiva de reunión RestrictedAnonymous de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="29916-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="29916-120">Usar el cmdlet New-CsBatchPolicyAssignmentOperation de datos</span><span class="sxs-lookup"><span data-stu-id="29916-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="29916-121">Con [la asignación de directivas](assign-policies.md#assign-a-policy-to-a-batch-of-users)por lotes, el número máximo de usuarios para los que puede quitar o actualizar directivas es de 5 000 a la vez.</span><span class="sxs-lookup"><span data-stu-id="29916-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="29916-122">Por ejemplo, si tiene más de 5.000 usuarios, tendrá que enviar varios lotes.</span><span class="sxs-lookup"><span data-stu-id="29916-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="29916-123">Para obtener los mejores resultados, no envíe varios lotes a la vez.</span><span class="sxs-lookup"><span data-stu-id="29916-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="29916-124">Permitir que los lotes completen el procesamiento antes de enviar más lotes.</span><span class="sxs-lookup"><span data-stu-id="29916-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="29916-125">El cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) se encuentra en el módulo Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29916-125">The [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="29916-126">Antes de seguir estos pasos, instale y conéctese al módulo [Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="29916-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="29916-127">Para obtener instrucciones paso a paso, vea [Instalar Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="29916-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="29916-128">Ejecute los siguientes comandos para quitar la directiva de reunión RestrictedAnonymousAccess de un lote de usuarios.</span><span class="sxs-lookup"><span data-stu-id="29916-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="29916-129">Obtener el estado de la asignación por lotes</span><span class="sxs-lookup"><span data-stu-id="29916-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="29916-130">Cada asignación por lotes devuelve un id. de operación, que puede usar para realizar un seguimiento del progreso y el estado de las asignaciones e identificar los errores que puedan producirse.</span><span class="sxs-lookup"><span data-stu-id="29916-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="29916-131">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="29916-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="29916-132">Asegúrese de que **ErrorCount** es **0** (cero) y **que OverallStatus** está **completado.**</span><span class="sxs-lookup"><span data-stu-id="29916-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="29916-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="29916-133">Related topics</span></span>

- [<span data-ttu-id="29916-134">Administración de directivas de reunión en Teams</span><span class="sxs-lookup"><span data-stu-id="29916-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="29916-135">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="29916-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="29916-136">Asignar directivas a los usuarios en Teams</span><span class="sxs-lookup"><span data-stu-id="29916-136">Assign policies to your users in Teams</span></span>](assign-policies.md)