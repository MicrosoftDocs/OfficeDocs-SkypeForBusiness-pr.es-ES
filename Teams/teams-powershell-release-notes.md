---
title: Notas de la versión de Microsoft Teams PowerShell
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga más información sobre los cambios más recientes en Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5859aeb74e8966138b91d16e206cbd9d00cf0587
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077685"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notas de la versión de Microsoft Teams PowerShell

Esta página proporciona el registro de cambios de PowerShell más reciente de Teams para la disponibilidad general y las versiones de versión preliminar pública.

## <a name="release-notes"></a>Notas de la versión

> [!NOTE]
> **-la vista previa** en la columna versión siguiente representa actualizaciones de la versión preliminar pública de Teams PowerShell.

| Fecha | Versión | Las |
|------- | -------------------- | ------------------------------ |
| 2020 de julio | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Se han agregado [cmdlets de asignación de directiva de grupo](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| 2020 de junio | [1.1.3: vista previa](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integración del conector de Skype empresarial online<li>Optimizaciones del equipo Get<li>Mayor confiabilidad</li> |
| 2020 de junio | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Se ha agregado la carga previa del cmdlet<li>Optimizaciones de .NET Framework</li>   |
| 2020 de abril | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode y firma de ensamblado<li>Se agregó Get-CsPolicyPackage<li>Se agregó Get-CsUserPolicyPackage<li>Se agregó Get-CsUserPolicyPackageRecommendation<li>Se ha agregado la concesión-CsUserPolicyPackage<li>Se ha agregado New-CsBatchPolicyPackageAssignmentOperation<li>Se agregó Set-TeamArchivedState<li>Se agregó Set-TeamPicture<li>Se ha quitado Get-TeamHelp</li>  |
| 2020 de marzo | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Se ha agregado New-CsBatchPolicyAssignmentOperation</li> |
| 2020 Feb | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Optimizaciones del equipo Get</li>  |

### <a name="cmdlet-availability"></a>Disponibilidad del cmdlet

> [!NOTE]
> La lista de la tabla siguiente solo incluye los cmdlets que forman parte de forma nativa del módulo Teams PowerShell. No se muestran los cmdlets de Teams en el[módulo de conectores de kype para empresas online](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) . Sin embargo, puesto que esos cmdlets se migran de forma nativa a teams PowerShell, los agregaremos a esta tabla.

| Cmdlet | Disponible en la versión preliminar pública | Disponible en GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sí | **No** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Sí | Sí |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sí | **No**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sí | Sí |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sí | Sí |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sí | Sí |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Sí | Sí |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Sí | **No** |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Sí | Sí |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Sí | Sí |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Sí | Sí|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Sí | Sí|
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Sí | Sí |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Sí | Sí |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Sí | Sí |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Sí | Sí |
| [Nuevo: CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Sí | Sí |
| [Nuevo: CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Sí | Sí |
| [Nuevo: CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Sí | Sí |
| [Nuevo: CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Sí | **No** |
| [Nuevo: equipo](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Sí | Sí |
| [Nuevo: TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Sí | Sí |
| [Nuevo: TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Sí | Sí |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Sí | Sí |
| [Quitar equipo](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Sí | Sí |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Sí | Sí |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Sí | Sí |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Sí | Sí |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Sí | **No** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Sí | **No**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Sí | Sí |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Sí | Sí |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Sí | Sí |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Sí | Sí |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Sí | Sí |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Sí | Sí |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Sí | Sí |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Sí | **No** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Sí | **No** |

## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Instalar Teams PowerShell](teams-powershell-install.md)

[Administración de equipos con Teams PowerShell](teams-powershell-managing-teams.md)

[Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
