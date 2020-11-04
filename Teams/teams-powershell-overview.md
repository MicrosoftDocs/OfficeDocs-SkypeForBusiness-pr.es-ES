---
title: Información general de Microsoft Teams PowerShell
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
# <a name="microsoft-teams-powershell-overview"></a>Información general de Microsoft Teams PowerShell

Microsoft Teams PowerShell es un conjunto de cmdlets para administrar equipos directamente desde la línea de comandos de PowerShell. Desarrollado en .NET Standard, Teams PowerShell funciona en PowerShell 5,1 en Windows, PowerShell 6. x y versiones posteriores en todas las plataformas, incluido el Shell en la nube de Azure.

Antes de empezar a usar PowerShell, tendrá que [instalarlo](teams-powershell-install.md). 

> [!WARNING]
> Hay problemas conocidos con PowerShell 7 y Teams. Le recomendamos que use el 5,1 de PowerShell hasta que se resuelvan los problemas.

## <a name="releases"></a>Ediciones


Teams PowerShell está disponible en la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en dos tipos de versiones.

- **Disponibilidad general (GA)** : cmdlets listos para producción, actualizados mensualmente.

- **Versión preliminar pública** : acceso anticipado a las características. Puede actualizarse con más frecuencia que la GA.

Para obtener información detallada sobre las adiciones y mejoras de características de las versiones, lea las notas de la [versión de Teams PowerShell](teams-powershell-release-notes.md).


## <a name="manage-teams-with-powershell"></a>Administrar equipos con PowerShell

Usarás los módulos de Teams PowerShell para administrar los equipos por completo:

- [Módulo Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): el módulo de PowerShell de Teams contiene cmdlets para administrar equipos, chats y canales.

> [!NOTE]
> La versión pública más reciente de [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada en el conector de Skype empresarial online y ofrece un único módulo para la administración de PowerShell de Teams.

- [Conector de Skype empresarial PowerShell](https://www.microsoft.com/download/details.aspx?id=39366): el conector de PowerShell de Skype empresarial ahora forma parte del módulo Teams PowerShell.

Para obtener una guía completa de la administración de equipos con estos módulos, consulte [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).


## <a name="related-topics"></a>Temas relacionados

[Instalar Teams PowerShell](teams-powershell-install.md)

[Administración de equipos con Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de la versión de Teams PowerShell](teams-powershell-release-notes.md)

[Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype empresarial](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md)
