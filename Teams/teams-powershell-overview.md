---
title: Microsoft Teams Información general de PowerShell
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
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams Información general de PowerShell

Microsoft Teams PowerShell es un conjunto de cmdlets para administrar Teams directamente desde la línea de comandos de PowerShell. Escrito en .NET Standard, Teams PowerShell funciona en PowerShell 5.1 en Windows, PowerShell 6.x y posteriores en todas las plataformas, incluido Azure Cloud Shell.

Antes de empezar a usar PowerShell, tendrá que [instalarlo.](teams-powershell-install.md) 

> [!WARNING]
> Hay problemas conocidos con PowerShell 7 y Teams PowerShell. Se recomienda usar PowerShell 5.1 hasta que se resuelvan los problemas.

## <a name="releases"></a>Versiones


Teams PowerShell está disponible en la [Galería de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en dos tipos de versión.

- **Disponibilidad general (GA):** cmdlets listos para producción, actualizados mensualmente.

- **Vista previa pública:** Acceso anticipado a las características. Es posible que se actualice con más frecuencia que GA.

Para obtener información detallada sobre las adiciones y mejoras de características de ambas versiones, lea las Teams de la versión [de PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Administrar Teams con PowerShell

Usará los módulos Teams PowerShell para administrar por completo Teams:

- [Microsoft Teams de PowerShell:](https://www.powershellgallery.com/packages/MicrosoftTeams/)el módulo Teams PowerShell contiene cmdlets para administrar equipos, chat y canales.

> [!NOTE]
> La Teams versión pública 2.0 o posterior de [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) incluye todos los cmdlets de Skype Empresarial Online Connector, lo que proporciona un único módulo para Teams administración de PowerShell.

- [Skype Empresarial conector de PowerShell:](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)el Skype Empresarial de PowerShell es ahora parte de Teams módulo de PowerShell.

Para obtener una guía completa sobre cómo administrar Teams estos módulos, vea Administrar Teams [con Teams PowerShell](teams-powershell-managing-teams.md).


## <a name="related-topics"></a>Temas relacionados

[Instalar Teams PowerShell](teams-powershell-install.md)

[Administrar Teams con Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notas de la versión de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams referencia de cmdlet](/powershell/teams/?view=teams-ps)

[Skype Empresarial referencia de cmdlet](/powershell/skype/intro?view=skype-ps)

[Usar los roles de administrador de Microsoft Teams para administrar Teams](using-admin-roles.md)
