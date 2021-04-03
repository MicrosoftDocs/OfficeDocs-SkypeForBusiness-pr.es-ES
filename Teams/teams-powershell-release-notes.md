---
title: Notas de la versión de PowerShell de Microsoft Teams
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
description: Obtenga información sobre los cambios más recientes en Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80e6225302cb733c37ba1720d95d8d8f1a220831
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506697"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notas de la versión de PowerShell de Microsoft Teams

Esta página proporciona el registro de cambios de PowerShell de Teams más reciente para las versiones de disponibilidad general y vista previa pública.

## <a name="release-notes"></a>Notas de la versión

> [!NOTE]
> **-preview en** la columna de versión siguiente representa las actualizaciones de la vista previa pública de PowerShell de Teams.

| Fecha | Versión | Actualizaciones |
|------- | -------------------- | ------------------------------ |
| Abril de 2021 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Se ha corregido el formato de los cmdlets existentes (por ejemplo, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy y mucho más).</li><li>Lista de parámetros actualizada de cmdlets de administración de directivas.</li>|
| Marzo de 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa MSAL para la autenticación & autorización</li> <li>Connect-MicrosoftTeams es el punto de entrada de todos los cmdlets.</li><li>New-csOnlineSession ya no está disponible. Se ha sustituido por Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection ya no es necesario. La característica se ha implementado de forma nativa en el módulo de PowerShell de Teams.</li> <li>Cmdlets de paquete de directivas refactorizado y agrega asignación de paquetes de grupo</li><li>Mejoras significativas de rendimiento para Get-Team cmdlet</li> <li>Opción de registro y depuración mejorada para cmdlets existentes </li> <li>Cmdlets de administración de plantillas agregados</li> <li>Desuso de New-CsOnlineSession</li>|
| Febrero de 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlets de administración de plantillas agregados</li><li>Mejoras de mezzo y procesamiento por lotes para Get-Team cmdlet</li> <li>Opción de registro y depuración mejorada para cmdlets existentes </li> <li>Cmdlets de paquete de directivas refactorizado</li>|
| Diciembre de 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Actualizaciones del cmdlet New-team con mayores reintentos y duración de suspensión</li>|
| Diciembre de 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Actualizaciones de integración de Skype Empresarial Online</li><li>Corrección del mensaje duplicado con Connect-Microsoft Teams</li>|
| Noviembre de 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Agrega cmdlets de paquetes de directivas personalizados</li><li>Correcciones para los comandos de carga de la jerarquía de destino</li>|
| Noviembre de 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa MSAL para la autenticación & autorización</li><li>Cmdlets de paquete de directivas refactorizado y agrega asignación de paquetes de grupo</li><li>Comandos de carga de jerarquía de segmentación refactorizado para usar un modelo asíncrono</li> <li>Se le pedirá al usuario dos veces durante la autenticación inicial cuando no use el parámetro -credential. Los usuarios pueden pasar credenciales con el parámetro -credential para evitar un mensaje duplicado. Este comportamiento se solucionará en la próxima versión.</li> |
| Septiembre de 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integración de Skype Empresarial Online Connector</li> |
| Septiembre de 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integración de Skype Empresarial Online Connector</li> |
| Julio de 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Cmdlets de [asignación de directivas de grupo agregados](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Junio de 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integración de Skype Empresarial Online Connector<li>Get-Team optimizaciones<li>Confiabilidad mejorada</li> |
| Junio de 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Se ha agregado la precarga del cmdlet<li>Optimizaciones de .Net Framework</li>   |
| Abril de 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Firma de autenticación y ensamblado<li>Se agregaron Get-CsPolicyPackage<li>Se agregaron Get-CsUserPolicyPackage<li>Se agregaron Get-CsUserPolicyPackageRecommendation<li>Se agregaron Grant-CsUserPolicyPackage<li>Se agregaron New-CsBatchPolicyPackageAssignmentOperation<li>Se agregaron Set-TeamArchivedState<li>Se agregaron Set-TeamPicture<li>Eliminado Get-TeamHelp</li>  |
| Marzo de 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Se agregaron New-CsBatchPolicyAssignmentOperation</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team optimizaciones</li>  |

### <a name="cmdlet-availability"></a>Disponibilidad del cmdlet

> [!NOTE]
> La lista de la tabla siguiente solo incluye cmdlets que forman parte nativa del módulo de PowerShell de Teams. Los cmdlets de Teams en el módulo S[kype para Business Online Connector](/powershell/skype/intro?view=skype-ps) no se muestran. Sin embargo, como esos cmdlets se migran de forma nativa a PowerShell de Teams, los agregaremos a esta tabla.

| Cmdlet | Disponible en versión preliminar pública | Disponible en GA |
| -| -- | --|
| [Add-TeamChannelUser](/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sí | **No** |
| [Add-TeamUser](/powershell/module/teams/add-teamuser?view=teams-ps) | Sí | Sí |
| [Add-TeamsAppInstallation](/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sí | **No**|
| [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sí | Sí |
| [Disconnect-MicrosoftTeams](/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sí | Sí |
| [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sí | Sí |
| [Get-CsGroupPolicyAssignmentOperation](/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | Sí | **No** |
| [Get-CsOnlinePowerShellEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | Sí | Sí |
| [Get-CsPolicyPackage](/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyPackage](/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyPackageRecommendation](/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Sí | Sí |
| [Get-Team](/powershell/module/teams/get-team?view=teams-ps) | Sí | Sí |
| [Get-TeamChannel](/powershell/module/teams/get-teamchannel?view=teams-ps) | Sí | Sí|
| [Get-TeamChannelUser](/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Sí | **No** |
| [Get-TeamUser](/powershell/module/teams/get-teamuser?view=teams-ps) | Sí | Sí |
| [Get-TeamsApp](/powershell/module/teams/get-teamsapp?view=teams-ps) | Sí | Sí |
| [Get-TeamsAppInstallation](/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Sí | **No** |
| [Grant-CsUserPolicyPackage](/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Sí | Sí |
| [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Sí | Sí |
| [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Sí | Sí |
| [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Sí | Sí |
| [New-CsOnlineSession](/powershell/module/skype/new-csonlinesession?view=skype-ps) | Sí | Sí |
| [Nuevo equipo](/powershell/module/teams/new-team?view=teams-ps) | Sí | Sí |
| [New-TeamChannel](/powershell/module/teams/new-teamchannel?view=teams-ps) | Sí | Sí |
| [New-TeamsApp](/powershell/module/teams/new-teamsapp?view=teams-ps) | Sí | Sí |
| [Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Sí | Sí |
| [Quitar-equipo](/powershell/module/teams/remove-team?view=teams-ps) | Sí | Sí |
| [Remove-TeamChannel](/powershell/module/teams/remove-teamchannel?view=teams-ps) | Sí | Sí |
| [Remove-TeamChannelUser](/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Sí | **No** |
| [Remove-TeamsApp](/powershell/module/teams/remove-teamsapp?view=teams-ps) | Sí | Sí |
| [Remove-TeamsAppInstallation](/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Sí | **No** |
| [Remove-TeamTargetingHierarchy](./set-up-your-team-hierarchy.md#remove-your-hierarchy) | Sí | **No**|
| [Remove-TeamUser](/powershell/module/teams/remove-teamuser?view=teams-ps) | Sí | Sí |
| [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Sí | **No** |
| [Set-Team](/powershell/module/teams/set-team?view=teams-ps) | Sí | Sí |
| [Set-TeamArchivedState](/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Sí | Sí |
| [Set-TeamChannel](/powershell/module/teams/set-teamchannel?view=teams-ps) | Sí | Sí |
| [Set-TeamPicture](/powershell/module/teams/set-teampicture?view=teams-ps) | Sí | Sí |
| [Set-TeamsApp](/powershell/module/teams/set-teamapp?view=teams-ps) | Sí | Sí |
| [Set-TeamTargetingHierarchy](/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Sí | **No** |
| [Update-TeamsAppInstallation](/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Sí | **No** |
| [Enable-CsOnlineSessionForReconnection](/skypeforbusiness/set-up-your-computer-for-windows-powershell/diagnose-problems-with-the-skype-for-business-online-connector) | **No** | **No** |


## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Instalación de Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Referencia de cmdlet de Microsoft Teams](/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](/powershell/skype/intro?view=skype-ps)
