---
title: Información general sobre PowerShell de Microsoft Teams
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Aprenda a usar los controles de PowerShell para administrar Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852161"
---
# <a name="microsoft-teams-powershell-overview"></a>Información general sobre PowerShell de Microsoft Teams

Microsoft Teams PowerShell es un conjunto de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell. Escrito en .NET Standard, Teams PowerShell funciona en PowerShell 5.1 en Windows, PowerShell 6.x y versiones posteriores en todas las plataformas, incluido Azure Cloud Shell.

Antes de empezar a usar PowerShell, debe [instalarlo.](teams-powershell-install.md) 

> [!WARNING]
> Hay problemas conocidos con PowerShell 7 y Teams PowerShell. Se recomienda usar PowerShell 5.1 hasta que se resuelvan los problemas.

## <a name="releases"></a>Versiones


Teams PowerShell está disponible en la galería [de PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) dos tipos de versión.

- **Disponibilidad general (GA):** cmdlets preparados para producción que se actualizan mensualmente.

- **Versión preliminar pública:** Acceso anticipado a características. Puede actualizarse con más frecuencia que GA.

Para obtener información detallada sobre las adiciones de características y las mejoras de ambas versiones, lea las [notas de la versión de PowerShell de Teams.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Administrar Teams con PowerShell

Usará los módulos de PowerShell de Teams para administrar teams por completo:

- [Módulo De PowerShell de Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)el módulo PowerShell de Teams contiene cmdlets para administrar equipos, chat y canales.

> [!NOTE]
> La última [versión pública de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams se integra con Skype Empresarial Online Connector, proporcionando un módulo único para la administración de PowerShell de Teams.

- [Conector de PowerShell de Skype](https://www.microsoft.com/download/details.aspx?id=39366)Empresarial: El conector de PowerShell de Skype Empresarial ahora forma parte del módulo PowerShell de Teams.

Para obtener una guía completa sobre la administración de Teams con estos módulos, consulte [Administrar equipos con PowerShell de Teams.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Temas relacionados

[Instalación de Teams powerShell](teams-powershell-install.md)

[Administrar Teams con PowerShell de Teams](teams-powershell-managing-teams.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md)
