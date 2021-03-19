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
ms.openlocfilehash: 159e73ff9f499538f830da6dd57c8ff7584e49cd
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874740"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notas de la versión de PowerShell de Microsoft Teams

Esta página proporciona el registro de cambios de PowerShell de Teams más reciente para las versiones de disponibilidad general y vista previa pública.

## <a name="release-notes"></a>Notas de la versión

> [!NOTE]
> **-preview en** la columna de versión siguiente representa las actualizaciones de la vista previa pública de PowerShell de Teams.

| Fecha | Versión | Actualizaciones |
|------- | -------------------- | ------------------------------ |
| Marzo de 2021 | [2.0](https://www.powershellgallery.com/packages/MicrosoftTeams/) | <li>Connect-MicrosoftTeams es el punto de entrada de todos los cmdlets.</li><li>New-csOnlineSession ya no se puede avaiable. Se ha sustituido por Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection ya no es necesario. La característica se ha implementado de forma nativa en el módulo de PowerShell de Teams.</li>|
| Noviembre de 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Correcciones y mejoras de errores</li>|
| Noviembre de 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Correcciones y mejoras de errores</li>|
| Marzo de 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Usa MSAL para la autenticación & autorización</li><li>Cmdlets de paquete de directivas refactorizado y agrega asignación de paquetes de grupo</li><li>Mejoras significativas de rendimiento para Get-Team cmdlet</li> <li>Opción de registro y depuración mejorada para cmdlets existentes </li> <li>Cmdlets de administración de plantillas agregados</li> <li>Desuso de New-CsOnlineSession</li>|
| Febrero de 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Cmdlets de administración de plantillas agregados</li><li>Mejoras de mezzo y procesamiento por lotes para Get-Team cmdlet</li> <li>Opción de registro y depuración mejorada para cmdlets existentes </li> <li>Cmdlets de paquete de directivas refactorizado</li>|
| Diciembre de 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Actualizaciones del cmdlet New-team con mayores reintentos y duración de suspensión</li>|
| Diciembre de 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Actualizaciones de integración de Skype Empresarial Online</li><li>Corrección del mensaje duplicado con Connect-Microsoft Teams</li>|
| Noviembre de 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Agrega cmdlets de paquetes de directivas personalizados</li><li>Correcciones para los comandos de carga de la jerarquía de destino</li>|
| Noviembre de 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Usa MSAL para la autenticación & autorización</li><li>Cmdlets de paquete de directivas refactorizado y agrega asignación de paquetes de grupo</li><li>Comandos de carga de jerarquía de segmentación refactorizado para usar un modelo asíncrono</li> <li>Se le pedirá al usuario dos veces durante la autenticación inicial cuando no use el parámetro -credential. Los usuarios pueden pasar credenciales con el parámetro -credential para evitar un mensaje duplicado. Este comportamiento se solucionará en la próxima versión.</li> |
| Septiembre de 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Integración de Skype Empresarial Online Connector</li> |
| Septiembre de 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Integración de Skype Empresarial Online Connector</li> |
| Julio de 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Cmdlets de [asignación de directivas de grupo agregados](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| Junio de 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Integración de Skype Empresarial Online Connector<li>Get-Team optimizaciones<li>Confiabilidad mejorada</li> |
| Junio de 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Se ha agregado la precarga del cmdlet<li>Optimizaciones de .Net Framework</li>   |
| Abril de 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Firma de autenticación y ensamblado<li>Se agregaron Get-CsPolicyPackage<li>Se agregaron Get-CsUserPolicyPackage<li>Se agregaron Get-CsUserPolicyPackageRecommendation<li>Se agregaron Grant-CsUserPolicyPackage<li>Se agregaron New-CsBatchPolicyPackageAssignmentOperation<li>Se agregaron Set-TeamArchivedState<li>Se agregaron Set-TeamPicture<li>Eliminado Get-TeamHelp</li>  |
| Marzo de 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Se agregaron New-CsBatchPolicyAssignmentOperation</li> |
| Feb 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team optimizaciones</li>  |

### <a name="cmdlet-availability"></a>Disponibilidad del cmdlet

> [!NOTE]
> La lista de la tabla siguiente solo incluye cmdlets que forman parte nativa del módulo de PowerShell de Teams. Los cmdlets de Teams en el módulo S[kype para Business Online Connector](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) no se muestran. Sin embargo, como esos cmdlets se migran de forma nativa a PowerShell de Teams, los agregaremos a esta tabla.

| Cmdlet | Disponible en versión preliminar pública | Disponible en GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Sí | **No** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Sí | Sí |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Sí | **No**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Sí | Sí |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Sí | Sí |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Sí | Sí |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | Sí | **No** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | Sí | Sí |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Sí | Sí |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Sí | Sí |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Sí | Sí |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Sí | Sí|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Sí | **No** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Sí | Sí |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Sí | Sí |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Sí | **No** |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Sí | Sí |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Sí | Sí |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Sí | Sí |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Sí | Sí |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession?view=skype-ps) | Sí | Sí |
| [Nuevo equipo](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Sí | Sí |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps) | Sí | Sí |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Sí | Sí |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Sí | Sí |
| [Quitar-equipo](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Sí | Sí |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Sí | Sí |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Sí | **No** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Sí | Sí |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Sí | **No** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#remove-your-hierarchy) | Sí | **No**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Sí | Sí |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Sí | **No** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Sí | Sí |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Sí | Sí |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Sí | Sí |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Sí | Sí |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Sí | Sí |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Sí | **No** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Sí | **No** |
| [Enable-CsOnlineSessionForReconnection](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/diagnose-problems-with-the-skype-for-business-online-connector) | **No** | **No** |


## <a name="related-topics"></a>Temas relacionados

[Descripción de PowerShell para Teams](teams-powershell-overview.md)

[Instalación de Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Referencia de cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
