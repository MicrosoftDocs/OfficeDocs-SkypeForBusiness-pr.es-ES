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
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768359"
---
# <a name="microsoft-teams-powershell-overview"></a>Información general sobre PowerShell de Microsoft Teams

Microsoft Teams PowerShell es un conjunto de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell. Escrito en .NET Standard, Teams PowerShell funciona en PowerShell 5.1 en Windows, PowerShell 6.x y versiones posteriores en todas las plataformas, incluido Azure Cloud Shell.

Antes de empezar a usar PowerShell, tendrá que [instalarlo.](teams-powershell-install.md) 

> [!WARNING]
> Hay problemas conocidos con PowerShell 7 y Teams PowerShell. Se recomienda usar PowerShell 5.1 hasta que se resuelvan los problemas.

## <a name="releases"></a>Versiones


Teams PowerShell está disponible en la Galería [de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en dos tipos de versión.

- **Disponibilidad general (GA):** cmdlets listos para producción, actualizados mensualmente.

- **Vista previa pública:** Acceso anticipado a las características. Es posible que se actualice con más frecuencia que GA.

Para obtener información detallada sobre las adiciones y mejoras de características para ambas versiones, lea las notas de la versión [de PowerShell de Teams.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Administrar Teams con PowerShell

Usará módulos de PowerShell de Teams para administrar por completo Teams:

- [Módulo De PowerShell de Microsoft Teams:](https://www.powershellgallery.com/packages/MicrosoftTeams/)el módulo de PowerShell de Teams contiene cmdlets para administrar equipos, chats y canales.

> [!NOTE]
> La versión pública 2.0 o posterior de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) de Teams incluye todos los cmdlets de Skype Empresarial Online Connector, lo que proporciona un único módulo para la administración de PowerShell de Teams.

- [Conector de PowerShell de Skype](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)Empresarial: el conector de PowerShell de Skype Empresarial ahora forma parte del módulo PowerShell de Teams.

Para obtener una guía completa sobre cómo administrar Teams con estos módulos, consulte Administrar [equipos con PowerShell de Teams.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Temas relacionados

[Instalación de Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Notas de la versión de PowerShell de Teams](teams-powershell-release-notes.md)

[Referencia de cmdlet de Microsoft Teams](/powershell/teams/?view=teams-ps)

[Referencia de cmdlet de Skype Empresarial](/powershell/skype/intro?view=skype-ps)

[Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md)
