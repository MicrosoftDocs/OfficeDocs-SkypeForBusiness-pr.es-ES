---
title: Crear equipos de administradores de personas en Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Obtenga información sobre cómo usar un script de PowerShell para crear un equipo para cada administrador con sus directos como miembros del equipo.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583679"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Crear equipos de administradores de personas en Microsoft Teams


Cuando despliegue Microsoft Teams, en lugar de iniciar con una "pizarra en blanco" (sin equipos ni canales), le recomendamos encarecidamente que configure un marco base de equipos y canales. Esto ayuda a evitar el "arrastre de equipo", en el que los usuarios crean varios equipos cuando deberían crear canales en los equipos existentes. Para ayudarle a empezar con una estructura de equipos y canales bien diseñada, hemos creado un script de PowerShell que crea un equipo para cada uno de los administradores de personas de primera y segunda línea, con los informes directos de cada jefe como miembros del equipo. Se trata de un script "de momento" (no actualiza los equipos o canales automáticamente cuando se agregan o quitan personas de una organización). Sin embargo, es una herramienta valiosa que puede usar para imponer algún orden en la estructura de Teams desde el principio. Este script lee su Azure AD, obtiene una lista de los administradores y sus informes directos. Usa esta lista para crear un equipo por administrador de personas. 

## <a name="how-to-use-the-powershell-script"></a>Cómo usar el script de PowerShell 

Para empezar, ejecute [los administradores](scripts/powershell-script-create-teams-from-managers-export-managers.md) de exportación y su script de directs (que presupone que ya ha ejecutado los módulos de PowerShell [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) y [Connect-MicrosoftTeams).](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) El *script Exportar administradores* y sus directos crea un archivo delimitado por tabulaciones (ExportedManagerDirects.txt) en el que se enumeran todos los administradores con sus informes directos. 

A continuación, ejecute el script [Crear nuevos equipos de administradores de personas.](scripts/powershell-script-create-teams-from-managers-new-teams.md) Este script se lee en el ExportedManagerDirects.txt archivo y crea un equipo para cada administrador, con los informes directos de ese administrador como miembros. Si alguno de los administradores o directos no está habilitado para Teams, el script los omite y no crea un equipo. (Revise el informe y, después, vuelva a ejecutar el script después de haber activado Teams para cualquier persona que lo necesite. El script no creará un segundo equipo para ningún administrador para el que ya ha creado un equipo).

Para cada equipo, el script crea un canal General y "Solo por diversión". 

## <a name="best-practices"></a>Procedimientos recomendados

- Pida a cada gestor que agregue el sitio web de comunicaciones de crisis de su organización como ficha al canal General de cada equipo. 

- Consulte la nueva aplicación Comunicaciones de crisis leyendo esta entrada del 8 de marzo de 2020: Coordinar comunicaciones de crisis usando [Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Temas relacionados

[Procedimientos recomendados para organizar equipos](best-practices-organizing.md)

[Crear un equipo que abarque toda la organización en Teams](create-an-org-wide-team.md)
