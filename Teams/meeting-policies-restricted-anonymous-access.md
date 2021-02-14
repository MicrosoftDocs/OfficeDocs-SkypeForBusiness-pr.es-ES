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
description: Obtenga información sobre cómo quitar la directiva de reunión RestrictedAnonymousAccess Teams de los usuarios de su organización.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806260"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Quitar a los usuarios la directiva de reunión de Teams RestrictedAnonymousAccess

[Las directivas de](meeting-policies-in-teams.md) reuniones de Microsoft Teams se usan para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización. 

Teams incluye una directiva integrada denominada RestrictedAnonymousAccess, que contiene opciones predefinidas que incluyen la restricción de que los usuarios anónimos inicien una reunión. (Los usuarios anónimos son usuarios que no se han autenticado). Los administradores no pueden modificar ni cambiar la configuración predefinida de la directiva de reunión.

En este artículo se muestra cómo usar PowerShell para quitar la directiva de reunión RestrictedAnonymousAccess de los usuarios que tienen asignada esta directiva. Para obtener más información sobre cómo administrar Teams con PowerShell, consulte Información [general de PowerShell de Teams.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Antes de empezar

Instale y conéctese al [módulo PowerShell de Skype Empresarial.](https://www.microsoft.com/download/details.aspx?id=39366) Para obtener instrucciones paso a paso, consulte [Instalar Microsoft Teams PowerShell.](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Obtener las asignaciones de directivas de reuniones de Teams para su organización

Ejecute lo siguiente para obtener las asignaciones de directivas de reuniones de Teams para su organización.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

En este ejemplo, se devuelve el resultado siguiente, que muestra que se ha asignado a dos usuarios la directiva de reunión RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Unassign the RestrictedAnonymous meeting policy from users

Para quitar la directiva de reunión RestrictedAnonymous de los usuarios, puede usar el cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) si tiene un número reducido de usuarios (por ejemplo, menos de 100 usuarios). Si tiene un gran número de usuarios (por ejemplo, más de 100 usuarios), es más eficaz usar el cmdlet  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) para enviar una operación por lotes.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Usar el cmdlet Grant-CsTeamsMeeting Policy

Ejecute lo siguiente para quitar la directiva de reunión RestrictedAnonymous de los usuarios.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Usar el cmdlet New-CsBatchPolicyAssignmentOperation programa

Con [la asignación de](assign-policies.md#assign-a-policy-to-a-batch-of-users)directivas por lotes, el número máximo de usuarios para los que puede quitar o actualizar directivas es de 5 000 a la vez. Por ejemplo, si tiene más de 5000 usuarios, tendrá que enviar varios lotes. Para obtener los mejores resultados, no envíe varios lotes a la vez. Permitir que los lotes completen el procesamiento antes de enviar más lotes.

> [!NOTE]
> El [cmdlet New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) se encuentra en el módulo De Teams PowerShell. Antes de seguir estos pasos, instale y conéctese al módulo [de PowerShell de Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams) Para obtener instrucciones paso a paso, consulte [Instalar Microsoft Teams PowerShell.](teams-powershell-install.md)

Ejecute los comandos siguientes para quitar la directiva de reunión RestrictedAnonymousAccess de un lote de usuarios.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Obtener el estado de la asignación por lotes

Cada asignación por lotes devuelve un id. de operación, que puede usar para realizar un seguimiento del progreso y el estado de las asignaciones e identificar los errores que pueden producirse. Por ejemplo, ejecute lo siguiente:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Asegúrese de que **ErrorCount** es **0** (cero) y **que OverallStatus** está **completado.**

## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de reunión en Teams](meeting-policies-in-teams.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Asignar directivas a los usuarios en Teams](assign-policies.md)
