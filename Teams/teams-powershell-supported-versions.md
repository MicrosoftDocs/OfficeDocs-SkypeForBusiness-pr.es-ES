---
title: 'Módulo PowerShell de Teams: versiones compatibles'
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga más información sobre las versiones compatibles con el Módulo de PowerShell de Teams, que se usa para la administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae244a16e934b70085b2193bee3ef21a277f7ed
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397291"
---
# <a name="teams-powershell-module---supported-versions"></a>Módulo PowerShell de Teams: versiones compatibles

Las versiones del Módulo de PowerShell (TPM) de Microsoft Teams en la serie 4.x.x o posterior son las únicas versiones compatibles ahora. Todas las versiones anteriores se han retirado por completo desde el 15 de junio de 2022 & dejarán de funcionar (publicación del Centro de mensajes de referencia: MC350371). 

Se recomienda actualizar a la última versión del módulo de PowerShell de Teams.


## <a name="important-notes"></a>Notas importantes

- Las notas de la versión de todas las versiones del módulo PowerShell de Teams pueden encontrarse en [las notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md).

- Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo. Por ejemplo, si originalmente usaste Install-Module, deberías usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.

  ```powershell
  Update-Module MicrosoftTeams
  ```

- Si actualiza desde el Módulo PowerShell de Teams versión 1.1.6, actualice los scripts para que los use `Connect-MicrosoftTeams` en lugar de `New-CsOnlineSession`.

- Durante la actualización, se recomienda no usar TPM 4.x.x/3.x.x junto con las versiones anteriores a la 3.0.0. Por ejemplo, no se recomienda usar las versiones 4.x.x & 2.6.0 juntas para diferentes operaciones administrativas en la misma organización.

- Cambios relacionados
  - Novedades a Get-CsOnlineUser & Get-CsOnlineVoiceUser en TPM 3.x.x y versiones posteriores: más [detalles en Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser) (publicación del Centro de mensajes: MC340774).

  - Cambios en la asignación de número de teléfono: más [detalles en Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & [Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) (publicación del centro de mensajes : MC316139).

  - Cambios de parámetros en Get-CsTenant: más [detalles en Get-CsTenant](/powershell/module/skype/get-cstenant) (publicación del centro de mensajes: MC365397).
  
  - Si los scripts usan cmdlets New/Set of Policy o Configuration con parámetros de tipo PSListModifier, se recomienda usar la versión más reciente (4.2.0 o posterior). Publicación del centro de mensajes como referencia: MC397428.

  - [Nuevo| Get]-CsCloudCallDataConnection cmdlets ahora son compatibles con las versiones 4.6.0 o posteriores (publicación del centro de mensajes - MC408993).

- Al usar TPM 4.x.x o posterior, se recomienda no usar ninguno de los cmdlets obsoletos o no admitidos que se [mencionan a continuación](#deprecated-cmdlets).

## <a name="deprecated-cmdlets"></a>Cmdlets en desuso

- Algunos de los cmdlets que han quedado en desuso recientemente se enumeran a continuación. Los detalles sobre el mismo pueden encontrarse en las respectivas documentación pública.
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint), Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- A continuación se enumeran los cmdlets que no son compatibles o relevantes para escenarios de Microsoft Teams.
  - [Obtener| Set]-CsUserPstnSettings
  - [Obtener| Conjunto| Habilitar| Disable]-CsMeetingRoom
  - [Grant| Obtener| Conjunto| Nuevo| Remove]-CsConferencingPolicy
  - [Grant| Obtener| Conjunto| Nuevo| Remove]-CsClientPolicy
  - [Grant| Get]-CsHostedVoicemailPolicy
  - [Grant| Obtener| Conjunto| Nuevo| Remove]-CsMobilityPolicy
  - [Grant| Get]-CsVoiceRoutingPolicy
  - [Grant| Obtener]-CsBroadcastMeetingPolicy
  - [Grant| Get]-CsCloudMeetingPolicy
  - [Grant| Get]-CsGraphPolicy
  - [Grant| Obtener| Conjunto| Nuevo| Remove]-CsExternalUserCommunicationPolicy
  - [Grant| Obtener| Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Obtener| Set]-CsBroadcastMeetingConfiguration
  - [Obtener| Set]-CsOAuthConfiguration
  - [Obtener| Set]-CsMeetingConfiguration
  - [Obtener| Set]-CsTenantHybridConfiguration
  - [Obtener| Set]-CsPushNotificationConfiguration
  - [Obtener| Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Obtener| Set]-CsTenantProvider
  - Get-CsHostingProvider
  - [Obtener| Conjunto| Registrarse| Anular registro]-CsHybridPSTNAppliance
  - [Obtener| Conjunto| Nuevo| Quitar]-CsHybridPSTNSite
  - [Obtener| Set]-CsHybridMediationServer
  - [Obtener| Conjunto| Nuevo| Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Obtener| Conjunto| Nuevo| Quitar]-CsTeamsPinnedApp
  - [Obtener| Conjunto| Nuevo| Remove]-CsTenantCatalogApp
  - [Obtener| Conjunto| Nuevo| Quitar]-CsGlobalCatalogApp
  - [Obtener| Conjunto| Nuevo| Remove]-CsDefaultCatalogApp
  - [Obtener| Conjunto| Nuevo| Quitar]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [Obtener| Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>Temas relacionados

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con PowerShell de Teams](teams-powershell-managing-teams.md)

[Referencia de cmdlets de Microsoft Teams](/powershell/module/teams)

[referencia de cmdlet de Skype Empresarial](/powershell/module/skype)
