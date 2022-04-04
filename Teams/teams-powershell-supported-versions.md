---
title: 'Teams de PowerShell: versiones compatibles'
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga información sobre las versiones compatibles con el Teams PowerShell, que se usa para la administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e292e3ea5659920bca6fe6f663afc53164da5b49
ms.sourcegitcommit: e3a4df81721abe83886714a7c3c798e4c0888c35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2022
ms.locfileid: "64617711"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams de PowerShell: versiones compatibles

Microsoft Teams de Módulo de PowerShell (TPM) de la serie 4.x.x o versiones posteriores serán las únicas versiones admitidas en el futuro. Todas las versiones anteriores están en la ruta de retirada. Se recomienda actualizar el módulo Teams PowerShell a la versión más reciente.



## <a name="new-organizations"></a>Nuevas organizaciones

Las organizaciones que se incorpore a Teams solo podrán usar el módulo de PowerShell Teams en la serie 4.x.x o posterior a partir del 1 de abril de 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizaciones actuales (sin TPM activo)

Las organizaciones que no hayan usado un módulo de PowerShell Teams en los últimos tres meses (22 de enero - 22 de marzo), solo podrán usar el módulo de PowerShell Teams en la serie 4.x.x o posterior a partir del 1 de abril de 2022.



## <a name="current-organizations-tpm-active"></a>Organizaciones actuales (TPM activo)

Las organizaciones que han estado usando un módulo de PowerShell en los últimos tres meses (22 de enero- 22 de marzo) solo podrán usar un módulo de PowerShell Teams en la serie 4.x.x o posterior a partir del 15 de junio de 2022. Teams Publicación del centro de mensajes para referencia: MC350371. 



## <a name="important-notes"></a>Notas importantes

- Las notas de la versión de todas las Teams del módulo de PowerShell se pueden encontrar en [Teams de la versión de PowerShell](teams-powershell-release-notes.md).

- Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo. Por ejemplo, si usó originalmente Install-Module, debe usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Si actualiza desde Teams módulo de PowerShell versión 1.1.6, actualice los scripts para usarlos `Connect-MicrosoftTeams` en lugar de `New-CsOnlineSession`.

-   Durante la actualización, se sugiere no usar TPM 4.x.x/3.x.x junto con versiones anteriores a 3.0.0. Por ejemplo, no se recomienda usar las versiones 4.x.x & 2.6.0 conjuntamente para diferentes operaciones de administrador de la misma organización. 

- Cambios relacionados
  * Actualizaciones de Get-CsOnlineUser & Get-CsOnlineVoiceUser TPM 3.x.x y versiones posteriores: más detalles en [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (publicación del centro de mensajes : MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Cambios que vienen Teléfono asignación de números: más detalles en [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Publicación del centro de mensajes : MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)

  * Desuso de Get-CsOnlineDirectoryTenant: más detalles en [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant) (publicación del centro de mensajes : MC346902).



## <a name="related-topics"></a>Temas relacionados

[Teams de la versión de PowerShell](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams referencia de cmdlet](/powershell/module/teams) 

[Skype Empresarial referencia de cmdlet](/powershell/module/skype) 
