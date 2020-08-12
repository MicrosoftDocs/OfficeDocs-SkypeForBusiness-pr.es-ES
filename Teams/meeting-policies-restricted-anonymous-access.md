---
title: Quitar la política de reunión de RestrictedAnonymousAccess Teams de los usuarios
author: LanaChin
ms.author: v-lanac
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
description: Aprenda a quitar la política de reunión de RestrictedAnonymousAccess Teams de los usuarios de su organización.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46641003"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Quitar la política de reunión de RestrictedAnonymousAccess Teams de los usuarios

[Las directivas de reunión](meeting-policies-in-teams.md) de Microsoft Teams se usan para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización. 

Teams incluye una directiva integrada denominada RestrictedAnonymousAccess, que contiene valores predefinidos que incluyen la restricción de que los usuarios anónimos inicien una reunión. (Los usuarios anónimos son usuarios que no se han autenticado). Los administradores no pueden modificar ni cambiar la configuración predefinida de la Directiva de la reunión.

En este artículo se muestra cómo usar PowerShell para quitar la Directiva de reunión RestrictedAnonymousAccess de los usuarios que tienen asignada esta Directiva. Para obtener más información sobre cómo administrar equipos con PowerShell, vea [información general de Teams PowerShell](teams-powershell-overview.md).

## <a name="before-you-start"></a>Antes de empezar

Instale y conecte con el [módulo de PowerShell de Skype empresarial](https://www.microsoft.com/download/details.aspx?id=39366). Para obtener instrucciones paso a paso, consulte [instalar Microsoft Teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obtener las asignaciones de las directivas de reunión de Teams de la organización

Ejecute lo siguiente para obtener las asignaciones de las directivas de reunión de Teams para su organización.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

En este ejemplo, se devuelve el siguiente resultado, que muestra que a dos usuarios se les asigna la Directiva de reunión RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Cancelar la asignación de la Directiva de reunión de RestrictedAnonymous de los usuarios

Para quitar la RestrictedAnonymous Directiva de reunión de los usuarios, puede usar el cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) si tiene un número reducido de usuarios (por ejemplo, menos de 100 usuarios). Si tiene un gran número de usuarios (por ejemplo, más de 100 usuarios), es más eficaz usar el cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) para enviar una operación por lotes.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Use el cmdlet Grant-CsTeamsMeeting de Directiva

Ejecute lo siguiente para quitar la RestrictedAnonymous Directiva de reunión de los usuarios.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Use el cmdlet New-CsBatchPolicyAssignmentOperation

Con la asignación de la [Directiva por lotes](assign-policies.md#assign-a-policy-to-a-batch-of-users), el número máximo de usuarios para el que puede quitar o actualizar directivas es 5.000 a la vez. Por ejemplo, si tiene más de 5.000 usuarios, tendrá que enviar varios lotes. Para obtener los mejores resultados, no envíe varios lotes a la vez. Permita que los lotes terminen de procesarse antes de enviar más lotes.

> [!NOTE]
> El cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) está en el módulo Teams PowerShell. Antes de seguir estos pasos, instale y conecte con el [módulo de PowerShell de Teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Para obtener instrucciones paso a paso, consulte [instalar Microsoft Teams PowerShell](teams-powershell-install.md).

Ejecute los siguientes comandos para quitar la Directiva de reunión RestrictedAnonymousAccess de un lote de usuarios.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obtener el estado de la asignación por lotes

Cada asignación de lote devuelve un identificador de operación, que puede usar para realizar un seguimiento del progreso y el estado de las asignaciones e identificar cualquier error que pueda producirse. Por ejemplo, ejecute lo siguiente:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Asegúrese de que la **ErrorCount** es **0** (cero) y de que **OverallStatus** está **completada**.

## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md)
- [Información general de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios de Teams](assign-policies.md)
