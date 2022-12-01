---
title: Crear equipos de administrador de personas en Microsoft Teams
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Obtenga información sobre cómo usar un script de PowerShell para crear un equipo para cada administrador con sus directos como miembros del equipo.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198932"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Crear equipos de administrador de personas en Microsoft Teams


Al implementar Microsoft Teams, en lugar de iniciarse con una "pizarra en blanco" (sin equipos ni canales), le recomendamos que configure un marco base de equipos y canales. Esto ayuda a evitar la "expansión de equipos", donde los usuarios crean numerosos equipos cuando deberían crear canales en equipos existentes. Para ayudarle a empezar con una estructura de equipos y canales bien diseñada, hemos creado un script de PowerShell que crea un equipo para cada uno de los administradores de personas de primera y segunda línea, con los informes directos de cada director como miembros del equipo. Se trata de un script "puntual" (no actualiza automáticamente los equipos o canales cuando se agregan o quitan personas de una organización). Pero es una herramienta valiosa que puede usar para imponer algún orden en la estructura de Teams desde el principio. Este script lee su Azure AD y obtiene una lista de administradores y sus informes directos. Usa esta lista para crear un equipo por administrador de personas. 

## <a name="how-to-use-the-powershell-script"></a>Cómo usar el script de PowerShell 

Para empezar, ejecute [los administradores de exportación y su script de directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (lo que supone que ya ha ejecutado los módulos de PowerShell [Connect-AzureAd](/powershell/module/azuread/connect-azuread) y [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) ). Los *administradores de exportación y su script de directs* crean un archivo delimitado por tabulaciones (ExportedManagerDirects.txt) que enumera a todos los administradores con sus informes directos. 

Después, ejecute el [script Crear nuevos equipos de administradores de personas](scripts/powershell-script-create-teams-from-managers-new-teams.md). Este script lee en el archivo de ExportedManagerDirects.txt y crea un equipo para cada administrador, con los informes directos de ese administrador como miembros. Si algún administrador o directo no está habilitado para Teams, el script los omite y no crea un equipo. (Revise el informe y vuelva a ejecutar el script después de haber activado Teams para cualquier persona que lo necesite. El script no creará un segundo equipo para ningún administrador para el que ya haya creado un equipo.

Para cada equipo, el script crea un canal General y "Just for fun". 

## <a name="best-practices"></a>Procedimientos recomendados

- Pida a cada administrador de personas que agregue el sitio web de comunicaciones de crisis de su organización como una pestaña al canal General de cada equipo. 

- Consulte la nueva aplicación Comunicaciones de crisis leyendo esta entrada de blog del 8 de marzo de 2020: [Coordinar las comunicaciones de crisis con Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Temas relacionados

[Procedimientos recomendados para organizar equipos](best-practices-organizing.md)

[Crear un equipo que abarque toda la organización en Teams](create-an-org-wide-team.md)