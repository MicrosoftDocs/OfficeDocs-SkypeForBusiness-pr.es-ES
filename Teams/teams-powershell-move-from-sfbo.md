---
title: Desplazarse desde el conector de Skype empresarial online al módulo de PowerShell de Teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a cambiar de conector de Skype empresarial online al módulo de Teams PowerShell para administrar equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469675"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Desplazarse desde el conector de Skype empresarial online al módulo de PowerShell de Teams

Para pasar de usar el conector de Skype empresarial online al módulo de PowerShell de Teams para administrar Teams, tendrá que actualizar los scripts de PowerShell existentes. En este artículo se explica cómo hacerlo.

1. Instale el módulo de PowerShell más reciente de Teams. Para conocer los pasos, consulte [instalar Microsoft Teams PowerShell](teams-powershell-install.md).
2. Desinstale el conector de Skype empresarial online. Para hacerlo, vaya a **programas y características**en el panel de control, seleccione **Skype empresarial online, módulo de Windows PowerShell**y, a continuación, seleccione **desinstalar**. 
3. En los scripts de PowerShell, cambie el nombre del módulo al que se hace referencia en ```Import-Module``` de ```SkypeOnlineConnector``` o ```LyncOnlineConnector``` a ```MicrosoftTeams``` .

    Por ejemplo, cambie ```Import-Module -Name SkypeOnlineConnector``` a ```Import-Module -Name MicrosoftTeams``` .

> [!NOTE]
> Los administradores deben seguir usando [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) e importar la sesión antes de usar los cmdlets de Skype empresarial online. 

## <a name="related-topics"></a>Temas relacionados

[Instalar Microsoft Teams PowerShell](teams-powershell-install.md)

[Administrar equipos con Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de la versión de Teams PowerShell](teams-powershell-release-notes.md)

[Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
