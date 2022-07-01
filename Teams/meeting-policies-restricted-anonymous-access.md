---
title: Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Obtenga información sobre cómo quitar la directiva de reunión de Teams RestrictedAnonymousAccess de los usuarios de su organización.
ms.openlocfilehash: e5ea203e52ca1b81ed7ce37f31c9f8cb5900c131
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564108"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess

[Las directivas de reunión](meeting-policies-overview.md) en Microsoft Teams se usan para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización. 

Teams incluye una directiva integrada denominada RestrictedAnonymousAccess, que contiene configuraciones predefinidas que incluyen la restricción de que los usuarios anónimos inicien una reunión. (Los usuarios anónimos son usuarios que no se han autenticado). Los administradores no pueden modificar ni modificar la configuración predefinida de la directiva de reunión.

En este artículo se muestra cómo usar PowerShell para quitar la directiva de reunión RestrictedAnonymousAccess de los usuarios que tienen asignada esta directiva. Para obtener más información sobre cómo administrar Teams con PowerShell, consulte [Introducción a PowerShell de Teams](teams-powershell-overview.md).

## <a name="before-you-start"></a>Antes de empezar

Instale y conéctese al [módulo Skype Empresarial PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell). Para obtener instrucciones detalladas, consulte [Instalar Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obtener las asignaciones de directivas de reunión de Teams para su organización

Ejecute lo siguiente para obtener las asignaciones de directivas de reunión de Teams para su organización.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

En este ejemplo, se devuelve la siguiente salida, que muestra que dos usuarios tienen asignada la directiva de reunión RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Anular la asignación de la directiva de reunión de RestrictedAnonymous a los usuarios

Para quitar la directiva de reunión RestrictedAnonymous de los usuarios, puede usar el cmdlet [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) si tiene un número reducido de usuarios (por ejemplo, menos de 100 usuarios). Si tiene un gran número de usuarios (por ejemplo, más de 100 usuarios), es más eficaz usar el cmdlet  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para enviar una operación por lotes.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Usar el cmdlet de directiva de Grant-CsTeamsMeeting

Ejecute lo siguiente para quitar la directiva de reunión RestrictedAnonymous de los usuarios.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Usar el cmdlet de New-CsBatchPolicyAssignmentOperation

Con la [asignación de directivas por lotes](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users), el número máximo de usuarios para los que puede quitar o actualizar directivas es de 5000 a la vez. Por ejemplo, si tiene más de 5000 usuarios, tendrá que enviar varios lotes. Para obtener los mejores resultados, no envíe varios lotes a la vez. Permita que los lotes completen el procesamiento antes de enviar más lotes.

> [!NOTE]
> El cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) se encuentra en el módulo PowerShell de Teams. Antes de seguir estos pasos, instale y conéctese al [módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Para obtener instrucciones detalladas, consulte [Instalar Microsoft Teams PowerShell](teams-powershell-install.md).

Ejecute los siguientes comandos para quitar la directiva de reunión RestrictedAnonymousAccess de un lote de usuarios.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obtener el estado de la asignación por lotes

Cada asignación por lotes devuelve un id. de operación, que puede usar para realizar un seguimiento del progreso y el estado de las asignaciones e identificar los errores que se pueden producir. Por ejemplo, ejecute lo siguiente:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Asegúrese de que **ErrorCount** es **0** (cero) y **OverallStatus** es **Completed**.

## <a name="related-topics"></a>Temas relacionados

- [Administración de directivas de reunión en Teams](meeting-policies-overview.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)