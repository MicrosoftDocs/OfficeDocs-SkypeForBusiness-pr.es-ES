---
title: Crear equipos de administración de personas en Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Aprenda a usar un script de PowerShell para crear un equipo para cada jefe con sus directos como miembros del equipo.
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
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Crear equipos de administración de personas en Microsoft Teams


Al implementar Microsoft Teams, en lugar de iniciar una "pizarra en blanco" (sin equipos ni canales), le recomendamos encarecidamente que configure un marco de trabajo base de Teams y canales. Esto ayuda a evitar la "proliferación de equipos", en la que los usuarios crean numerosos equipos cuando deberían crear canales en los equipos existentes. Para ayudarle a comenzar a usar una estructura de equipos y canales bien diseñada, hemos creado un script de PowerShell que crea un equipo para cada uno de sus administradores de contactos de primera y segunda línea, con los informes directos de cada Gerente como miembros del equipo. Este es un script "puntual" (no actualiza los equipos ni los canales de forma automática cuando se agregan o quitan usuarios de una organización). Pero es una herramienta valiosa que puede usar para imponer algún pedido en la estructura de su equipo desde el principio. Este script lee su Azure AD, obtiene una lista de administradores y sus subordinados directos. Usa esta lista para crear un equipo por administrador de personas. 

## <a name="how-to-use-the-powershell-script"></a>Cómo usar el script de PowerShell 

Para empezar, ejecute los [administradores de exportación y sus secuencias de comandos de Direct](scripts/powershell-script-create-teams-from-managers-export-managers.md) (lo cual supone que ya ha ejecutado los módulos [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) y [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell). Los *administradores de exportaciones y sus* scripts directos crean un archivo delimitado por tabulaciones (ExportedManagerDirects.txt) que enumera a todos los administradores con sus subordinados directos. 

A continuación, ejecute el [script de Teams crear nuevo jefe de contactos](scripts/powershell-script-create-teams-from-managers-new-teams.md). Este script lee el archivo de ExportedManagerDirects.txt y crea un equipo para cada director, con los informes directos de ese administrador como miembros. Si algún administrador o directo no está habilitado para Teams, el script lo omite y no crea un equipo. (Revise el informe y vuelva a ejecutar el script una vez que haya activado Teams para cualquiera que lo necesite. La secuencia de comandos no creará un segundo equipo para cualquier administrador para el que ya haya creado un equipo.

Para cada equipo, el script crea un canal general y "solo para el entretenimiento". 

## <a name="best-practices"></a>Procedimientos recomendados

- Pídale al administrador de cada persona que agregue el sitio web de comunicaciones de crisis de su organización como una ficha al canal general de cada equipo. 

- Consulta la nueva aplicación de comunicaciones de crisis leyendo la publicación del blog del 8 de marzo de 2020: [coordina las comunicaciones de crisis con Microsoft Teams + plataforma de energía](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Temas relacionados

[Procedimientos recomendados para organizar equipos](best-practices-organizing.md)

[Crear un equipo que abarque toda la organización en Teams](create-an-org-wide-team.md)
