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
ms.openlocfilehash: 9254afde824f072f6015531b90f4cacfb38acafe
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63689178"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams de PowerShell: versiones compatibles

Microsoft Teams de Módulo de PowerShell (TPM) de la serie 4.x.x serán las únicas versiones admitidas en el futuro. Todas las versiones anteriores están en la ruta de retirada.



## <a name="new-organizations"></a>Nuevas organizaciones

Las organizaciones que se incorpore a Teams solo podrán usar Teams módulo de PowerShell 4.0.0 o posterior a partir del 1 de abril de 2022.



## <a name="current-organizations-non-tpm-active"></a>Organizaciones actuales (sin TPM activo)

Las organizaciones que no hayan usado TPM en los últimos tres meses (22 de enero- 22 de marzo), solo podrán usar TPM 4.0.0 o posterior a partir del 1 de abril de 2022.



## <a name="current-organizations-tpm-active"></a>Organizaciones actuales (TPM activo)

Las organizaciones que han estado usando TPM en los últimos tres meses (22 de enero - 22 de marzo) tendrán más tiempo para actualizar a TPM 4.x.x. Más detalles para seguir pronto.



## <a name="important-notes"></a>Notas importantes

- Las notas de la versión de todas las Teams del módulo de PowerShell se pueden encontrar en [Teams de la versión de PowerShell](teams-powershell-release-notes.md).

- Para actualizar cualquier módulo de PowerShell, debe usar el mismo método usado para instalar el módulo. Por ejemplo, si usó originalmente Install-Module, debe usar [Update-Module](/powershell/module/powershellget/update-module) para obtener la versión más reciente.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Si actualiza desde Teams módulo de PowerShell versión 1.1.6, actualice los scripts para usarlos `Connect-MicrosoftTeams` en lugar de `New-CsOnlineSession`.

-   Durante la actualización, se sugiere no usar TPM 4.x.x/3.x.x junto con versiones anteriores a 3.0.0. Por ejemplo, no se recomienda usar las versiones 4.0.0 & 2.6.0 para diferentes operaciones de administrador de la misma organización. 

- Cambios relacionados
  * Actualizaciones de Get-CsOnlineUser & Get-CsOnlineVoiceUser TPM 3.0.0 y posteriores: más detalles en [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) &  (publicación del centro de mensajes : MC340774).[](/powershell/module/skype/get-csonlinevoiceuser)

  * Cambios que vienen Teléfono asignación de números: más detalles en [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) &  (Publicación del centro de mensajes : MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>Temas relacionados

[Teams de la versión de PowerShell](teams-powershell-release-notes.md)

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams referencia de cmdlet](/powershell/module/teams) 

[Skype Empresarial referencia de cmdlet](/powershell/module/skype) 
