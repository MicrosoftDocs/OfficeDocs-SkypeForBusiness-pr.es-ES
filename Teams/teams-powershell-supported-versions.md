---
title: 'Módulo Teams PowerShell: versiones compatibles'
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga más información sobre las versiones compatibles con el módulo de PowerShell Teams, que se usa para la administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e557a8ca4e8dff5489dbf729a137d73f9ca13c85
ms.sourcegitcommit: 5fe5516f6118ce3fa0449ab194a6fe87bf48c664
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64732288"
---
# <a name="teams-powershell-module---supported-versions"></a>Módulo Teams PowerShell: versiones compatibles

Microsoft Teams versiones del Módulo PowerShell (TPM) de la serie 4.x.x o posteriores serán las únicas versiones compatibles en el futuro. Todas las versiones anteriores están en la ruta de retirada. Se recomienda actualizar Teams módulo de PowerShell a la versión más reciente.



## <a name="new-organizations"></a>Nuevas organizaciones

Las organizaciones que se incorpore recientemente a Teams solo podrán usar Teams módulo de PowerShell en la serie 4.x.x o posterior a partir del 1 de abril de 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizaciones actuales (no tpm activo)

Las organizaciones que no hayan usado Teams módulo de PowerShell en los últimos tres meses (del 22 de enero al 22 de marzo) solo podrán usar Teams módulo de PowerShell en la serie 4.x.x o posterior a partir del 1 de abril de 2022.



## <a name="current-organizations-tpm-active"></a>Organizaciones actuales (TPM activo)

Las organizaciones que han estado usando Teams módulo de PowerShell en los últimos tres meses (22 de enero a marzo de 22), solo podrán usar Teams módulo de PowerShell en la serie 4.x.x o posterior a partir del 15 de junio de 2022. Publicación del centro de mensajes como referencia: MC350371. 



## <a name="important-notes"></a>Notas importantes

- Las notas de la versión de todas las versiones del módulo Teams PowerShell pueden encontrarse en [Teams notas de la versión de PowerShell](teams-powershell-release-notes.md).

- Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo. Por ejemplo, si originalmente usaste Install-Module, deberías usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Si actualiza desde Teams versión 1.1.6 del Módulo PowerShell, actualice los scripts para que se usen `Connect-MicrosoftTeams` en lugar de `New-CsOnlineSession`.

-   Durante la actualización, se recomienda no usar TPM 4.x.x/3.x.x junto con las versiones anteriores a la 3.0.0. Por ejemplo, no se recomienda usar las versiones 4.x.x & 2.6.0 juntas para diferentes operaciones administrativas en la misma organización. 

- Cambios relacionados
  * Actualizaciones de Get-CsOnlineUser & Get-CsOnlineVoiceUser en TPM 3.x.x y versiones posteriores: más [detalles en Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (publicación del Centro de mensajes: MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Cambios que llegarán a Teléfono asignación de número: más [detalles en Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (publicación del centro de mensajes – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)

-   Al usar TPM 4.x.x o posterior, se recomienda no usar ninguno de los cmdlets obsoletos o no admitidos que se [mencionan a continuación](#deprecated-cmdlets). 



## <a name="deprecated-cmdlets"></a>Cmdlets en desuso

- Algunos de los cmdlets que han quedado en desuso recientemente se enumeran a continuación. Los detalles sobre el mismo pueden encontrarse en las respectivas documentación pública. 
  * [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  * [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  * [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  * [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
  * [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  
  * [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  * [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)


- A continuación se enumeran los cmdlets que no son compatibles o relevantes para escenarios de Microsoft Teams. 
  * [Obtener| Set]-CsUserPstnSettings
  * [Obtener| Conjunto| Habilitar| Disable]-CsMeetingRoom
  * [Grant| Obtener| Conjunto| Nuevo| Remove]-CsConferencingPolicy
  * [Grant| Obtener| Conjunto| Nuevo| Remove]-CsClientPolicy
  * [Grant| Get]-CsHostedVoicemailPolicy
  * [Grant| Obtener| Conjunto| Nuevo| Remove]-CsMobilityPolicy
  * [Grant| Obtener] CsVoiceRoutingPolicy
  * [Grant| Obtener]-CsBroadcastMeetingPolicy
  * [Grant| Get]-CsCloudMeetingPolicy
  * [Grant| Get]-CsGraphPolicy
  * [Grant| Obtener| Conjunto| Nuevo| Remove]-CsExternalUserCommunicationPolicy
  * [Grant| Obtener| Set]-CsIPPhonePolicy
  * Get-CsUserServicesPolicy
  * [Obtener| Set]-CsBroadcastMeetingConfiguration
  * [Obtener| Set]-CsOAuthConfiguration
  * [Obtener| Set]-CsMeetingConfiguration
  * [Obtener| Set]-CsTenantHybridConfiguration
  * [Obtener| Set]-CsPushNotificationConfiguration
  * [Obtener| Set]-CsUCPhoneConfiguration
  * Get-CsImFilterConfiguration
  * Get-CsAudioConferencingProvider
  * [Obtener| Set]-CsTenantProvider
  * [Obtener| Conjunto| Registrarse| Anular registro]-CsHybridPSTNAppliance
  * [Obtener| Conjunto| Nuevo| Quitar]-CsHybridPSTNSite
  * [Obtener| Conjunto]- CsHybridMediationServer
  * [Obtener| Conjunto| Nuevo| Remove]-CsTenantUpdateTimeWindow
  * Get-CsUserLocationStatus
  * Invoke-CsUcsRollback
  * [Obtener| Conjunto| Nuevo| Quitar]-CsTeamsPinnedApp
  * [Obtener| Conjunto| Nuevo| Remove]-CsTenantCatalogApp
  * [Obtener| Conjunto| Nuevo| Quitar]-CsGlobalCatalogApp
  * [Obtener| Conjunto| Nuevo| Remove]-CsDefaultCatalogApp
  * [Obtener| Conjunto| Nuevo| Quitar]-CsTeamsAppPreset



## <a name="related-topics"></a>Temas relacionados

[Teams notas de la versión de PowerShell](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con PowerShell Teams](teams-powershell-managing-teams.md)

[referencia de cmdlet de Microsoft Teams](/powershell/module/teams) 

[referencia de cmdlet de Skype Empresarial](/powershell/module/skype) 
