---
title: Pasar del conector de Skype Empresarial Online al módulo de PowerShell de Teams
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
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469675"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Pasar del conector de Skype Empresarial Online al módulo de PowerShell de Teams

Para pasar del uso de Skype Empresarial Online Connector al módulo de PowerShell de Teams para administrar Teams, deberá actualizar sus scripts de PowerShell existentes. En este artículo se explica cómo hacerlo.

1. Instale el módulo de PowerShell más reciente de Teams. Para ver los pasos, [consulte Instalar Microsoft Teams PowerShell.](teams-powershell-install.md)
2. Desinstale Skype Empresarial Online Connector. Para ello, en el Panel de control, vaya a Programas y **características,** seleccione Skype Empresarial **Online, Windows PowerShell Module** y, a continuación, seleccione **Desinstalar.** 
3. En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia ```Import-Module``` desde ```SkypeOnlineConnector``` o a ```LyncOnlineConnector``` ```MicrosoftTeams``` .

    Por ejemplo, cambie ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Los administradores deben seguir usando [New-CsOnlineSession e](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) importar la sesión antes de usar los cmdlets de Skype Empresarial Online. 

## <a name="related-topics"></a>Temas relacionados

[Instalar Microsoft Teams Powershell](teams-powershell-install.md)

[Administrar Teams con PowerShell de Teams](teams-powershell-managing-teams.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
