---
title: Grupos de Microsoft 365 y Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo funcionan las pertenencias a grupos y grupos de Microsoft 365 con Microsoft Teams.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456084"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Grupos de Microsoft 365 y Microsoft Teams

Grupos de Microsoft 365 es el servicio de pertenencia entre aplicaciones de Microsoft 365. En un nivel básico, un grupo de Microsoft 365 es un objeto en Azure Active Directory con una lista de miembros y una gran carga de trabajo relacionada que incluye un sitio de grupo de SharePoint, un buzón de Exchange compartido, Planner y un área de trabajo de Power BI. Puede agregar o quitar usuarios al grupo como lo haría con cualquier otro objeto de seguridad basado en grupo en Active Directory.

![Diagrama que muestra grupos de Microsoft 365 y servicios relacionados](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

De forma predeterminada, los usuarios de Microsoft 365 pueden crear y administrar grupos. Para obtener más información sobre Grupos de Microsoft 365, vea Más información sobre Grupos de [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) y los Grupos de [Microsoft 365 para](teams-architecture-solutions-posters.md#groups-in-microsoft-365) póster de arquitectos de TI.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Cómo funcionan los Grupos de Microsoft 365 con Teams

Al crear un equipo, se crea un grupo de Microsoft 365 para administrar la pertenencia al equipo. Los servicios relacionados del grupo, como un sitio de SharePoint, un área de trabajo de Power BI, etc. se crean al mismo tiempo.

Las personas que crean equipos pueden optar por usar un grupo de Microsoft 365 existente si es propietario de ese grupo. Cada canal del equipo tiene una carpeta diferente en la biblioteca de documentos. La creación de carpetas directamente en la biblioteca de documentos no crea canales en el equipo.

Al crear un grupo de Microsoft 365 en Outlook o SharePoint, el buzón de grupo es visible en Outlook. Al crear un equipo en Teams, el buzón de grupo está oculto de forma predeterminada. Puede usar el cmdlet [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) con el parámetro **HiddenFromExchangeClientsEnabled** para hacer que un buzón sea visible.

## <a name="group-membership"></a>Pertenencia a grupos

Si quita a un miembro de un equipo, también se quita del grupo de Microsoft 365. La eliminación del grupo quita inmediatamente el equipo y los canales del cliente de Teams. Si quita a una persona de un grupo mediante el Centro de administración de Microsoft 365, ya no tendrá acceso a otros aspectos de colaboración, como la biblioteca de documentos de SharePoint Online, el grupo de Yammer o oneNote compartido. Sin embargo, seguirán teniendo acceso a la funcionalidad de chat del equipo durante aproximadamente dos horas.

Como práctica recomendada para administrar los miembros del equipo, agrégrélos y quítelos del cliente de Teams para asegurarse de que las actualizaciones de permisos para otras cargas de trabajo conectadas al grupo se produzcan rápidamente. Si agrega o quita miembros del equipo fuera del cliente de Teams (mediante el Centro de administración de Microsoft 365, Azure AD o Exchange Online PowerShell), pueden pasar hasta 24 horas hasta que los cambios se reflejen en Teams.

## <a name="deleting-groups-and-teams"></a>Eliminar grupos y equipos

Al eliminar un grupo de Microsoft 365, se quitará el alias de buzón para las conversaciones persistentes de Outlook/OWA y las invitaciones a reuniones de Teams, y se marcará el sitio de SharePoint para su eliminación. La eliminación de un equipo y su efecto en Outlook tardan unos 20 minutos. Al eliminar un equipo desde el cliente de Teams, este se quitará inmediatamente de la vista para todos los miembros del equipo. Si quita miembros de un grupo de Microsoft 365 que tenía habilitada la funcionalidad de Teams, podría haber un retraso de aproximadamente dos horas antes de que se quite el equipo de la vista en el cliente de Teams para las personas afectadas que se quitaron.

Para obtener información detallada sobre las opciones de finalización del ciclo de vida de grupos y equipos, vea Opciones de final del ciclo de vida de [grupos,](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) equipos y Yammer y Archivar o eliminar un equipo [en Microsoft Teams.](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)

## <a name="related-topics"></a>Temas relacionados

[Bases de Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar un grupo eliminado](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)