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
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712964"
---
# <a name="teams-powershell-module---supported-versions"></a>Módulo Teams PowerShell: versiones compatibles

Microsoft Teams versiones del Módulo PowerShell (TPM) de la serie 4.x.x o posteriores serán las únicas versiones compatibles en el futuro. Todas las versiones anteriores están en la ruta de retirada. Se recomienda actualizar Teams módulo de PowerShell a la versión más reciente.



## <a name="new-organizations"></a>Nuevas organizaciones

Las organizaciones que se incorpore recientemente a Teams solo podrán usar Teams módulo de PowerShell en la serie 4.x.x o posterior a partir del 1 de abril de 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizaciones actuales (no tpm activo)

Las organizaciones que no hayan usado Teams módulo de PowerShell en los últimos tres meses (del 22 de enero al 22 de marzo) solo podrán usar Teams módulo de PowerShell en la serie 4.x.x o superior a partir del 1 de abril de 2022.



## <a name="current-organizations-tpm-active"></a>Organizaciones actuales (TPM activo)

Las organizaciones que han estado usando Teams módulo de PowerShell en los últimos tres meses (22 de enero a marzo de 22), solo podrán usar Teams módulo de PowerShell en la serie 4.x.x o superior a partir del 15 de junio de 2022. Publicación del centro de mensajes como referencia: MC350371. 



## <a name="important-notes"></a>Notas importantes

- Las notas de la versión de todas las versiones del módulo Teams PowerShell pueden encontrarse en [Teams notas de la versión de PowerShell](teams-powershell-release-notes.md).

- Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo. Por ejemplo, si originalmente usaste Install-Module, deberías usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Si actualiza desde Teams versión 1.1.6 del Módulo PowerShell, actualice los scripts para que se usen `Connect-MicrosoftTeams` en lugar de `New-CsOnlineSession`.

-   Durante la actualización, se recomienda no usar TPM 4.x.x/3.x.x junto con versiones anteriores a la 3.0.0. Por ejemplo, no se recomienda usar las versiones 4.x.x & 2.6.0 juntas para diferentes operaciones administrativas en la misma organización. 

- Cambios relacionados
  * Actualizaciones de Get-CsOnlineUser & Get-CsOnlineVoiceUser en TPM 3.x.x y posteriores: más [detalles en Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (publicación del Centro de mensajes: MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Cambios que llegarán a Teléfono asignación de número: más [detalles en Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (publicación del centro de mensajes – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>Cmdlets en desuso

A continuación se muestran algunos de los cmdlets que han quedado en desuso recientemente o que no son compatibles con Microsoft Teams escenarios. Los detalles sobre el mismo pueden encontrarse en las respectivas documentación pública. 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings), [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom), [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom), [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom), [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>Temas relacionados

[Teams notas de la versión de PowerShell](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con PowerShell Teams](teams-powershell-managing-teams.md)

[referencia de cmdlet de Microsoft Teams](/powershell/module/teams) 

[referencia de cmdlet de Skype Empresarial](/powershell/module/skype) 
