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
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094416"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Crear equipos de administradores de personas en Microsoft Teams


Al ejecutar Microsoft Teams, en lugar de iniciar con una "pizarra en blanco" (sin equipos ni canales), le recomendamos encarecidamente que configure un marco base de equipos y canales. Esto ayuda a evitar la "expansión del equipo", donde los usuarios crean numerosos equipos cuando deben crear canales en equipos existentes. Para ayudarle a empezar con una estructura de equipos y canales bien diseñada, hemos creado un script de PowerShell que crea un equipo para cada uno de los administradores de personas de primera y segunda línea, con los informes directos de cada administrador como miembros del equipo. Se trata de un script "a tiempo" (no actualiza los equipos o canales automáticamente cuando se agregan o quitan personas de una organización). Pero es una herramienta valiosa que puede usar para imponer algún orden en su estructura Teams desde el principio. Este script lee Azure AD, obtiene una lista de administradores y sus informes directos. Usa esta lista para crear un equipo por cada administrador de personas. 

## <a name="how-to-use-the-powershell-script"></a>Cómo usar el script de PowerShell 

Empiece ejecutando los administradores de exportación y su script de directs (lo que supone que ya ha ejecutado los [módulos](scripts/powershell-script-create-teams-from-managers-export-managers.md) [de PowerShell Conectar-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) [y Conectar-MicrosoftTeams).](/powershell/module/teams/connect-microsoftteams?view=teams-ps) El *script Exportar administradores y* sus directos crea un archivo delimitado por tabulaciones (ExportedManagerDirects.txt) que enumera todos los administradores con sus informes directos. 

A continuación, ejecute el script [Crear nuevos equipos de administrador de personas.](scripts/powershell-script-create-teams-from-managers-new-teams.md) Este script se lee en el ExportedManagerDirects.txt y crea un equipo para cada administrador, con los informes directos de ese administrador como miembros. Si algún administrador o directo no está habilitado para Teams, el script los omite y no crea un equipo. (Revise el informe y vuelva a ejecutar el script después de haber activado Teams para cualquier persona que lo necesite. El script no creará un segundo equipo para ningún administrador para el que ya haya creado un equipo).

Para cada equipo, el script crea un canal General y "Solo por diversión". 

## <a name="best-practices"></a>Procedimientos recomendados

- Pida a cada administrador de personas que agregue el sitio web de comunicaciones por crisis de su organización como pestaña al canal General de cada equipo. 

- Consulte la nueva aplicación Crisis Communications leyendo esta entrada de blog del 8 de marzo de 2020: Coordinar las comunicaciones de [crisis con Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Temas relacionados

[Procedimientos recomendados para organizar equipos](best-practices-organizing.md)

[Crear un equipo que abarque toda la organización en Teams](create-an-org-wide-team.md)