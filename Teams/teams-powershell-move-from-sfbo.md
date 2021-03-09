---
title: Pasar de Skype Empresarial Online Connector al módulo de PowerShell de Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo pasar de Skype Empresarial Online Connector al módulo de PowerShell de Teams para administrar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569086"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Pasar de Skype Empresarial Online Connector al módulo de PowerShell de Teams

Para pasar de usar Skype Empresarial Online Connector al módulo de PowerShell de Teams para administrar Teams, tendrá que actualizar los scripts de PowerShell existentes. En este artículo se explica cómo hacerlo.

1. Instale el módulo de PowerShell de Teams más reciente. Para ver los pasos, [vea Instalar Microsoft Teams Powershell](teams-powershell-install.md).
2. Desinstale Skype Empresarial Online Connector. Para ello, en el Panel de control, vaya a Programas y **características,** seleccione Skype Empresarial **Online, Windows PowerShell Módulo** y, a continuación, **seleccione Desinstalar**. 
3. En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia ```Import-Module``` desde ```SkypeOnlineConnector``` o a ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Por ejemplo, cambie ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .
4. Al usar El módulo de PowerShell de Teams 2.0 o posterior, cambie New-csOnlineSession a Connect-MicrosoftTeams. 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>Temas relacionados

[Instalar Microsoft Teams Powershell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
