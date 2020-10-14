---
title: Microsoft 365 Groups y Microsoft Teams
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
description: Obtenga más información acerca de cómo los grupos y pertenencias a grupos de Microsoft 365 funcionan con Microsoft Teams.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456084"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Groups y Microsoft Teams

Microsoft 365 Groups es el servicio de suscripción entre aplicaciones de Microsoft 365. En un nivel básico, un grupo de Microsoft 365 es un objeto de Azure Active Directory con una lista de miembros y un acoplamiento a las cargas de trabajo relacionadas, incluidos un sitio de grupo de SharePoint, un buzón compartido de Exchange, Planner y un área de trabajo de Power BI. Puede Agregar o quitar personas del grupo de la misma manera que cualquier otro objeto de seguridad basado en grupos en Active Directory.

![Diagrama que muestra los grupos y los servicios relacionados de Microsoft 365](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

De forma predeterminada, los usuarios de Microsoft 365 pueden crear y administrar grupos. Para obtener más información sobre los grupos de Microsoft 365, consulte más información sobre los grupos de [microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) y los [grupos de Microsoft 365 para póster de arquitectos de ti](teams-architecture-solutions-posters.md#groups-in-microsoft-365) .

## <a name="how-microsoft-365-groups-work-with-teams"></a>Cómo funcionan los grupos de Microsoft 365 con Teams

Al crear un equipo, se crea un grupo de Microsoft 365 para administrar la pertenencia a un equipo. Los servicios relacionados con el grupo, como un sitio de SharePoint, un área de trabajo de Power BI, etc., se crean al mismo tiempo.

Las personas que crean equipos pueden optar por usar un grupo de Microsoft 365 existente si son propietarios de ese grupo. Cada canal del equipo tiene una carpeta independiente en la biblioteca de documentos. La creación de carpetas directamente en la biblioteca de documentos no crea canales en el equipo.

Al crear un grupo de Microsoft 365 en Outlook o SharePoint, el buzón de grupo está visible en Outlook. Al crear un equipo en Teams, el buzón del grupo se oculta de forma predeterminada. Puede usar el cmdlet [set-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) con el parámetro **HiddenFromExchangeClientsEnabled** para hacer visible un buzón.

## <a name="group-membership"></a>Pertenencia a grupos

Si quita un miembro de un equipo, también se quitará del grupo Microsoft 365. La eliminación del grupo elimina el equipo y los canales inmediatamente del cliente de Teams. Si quita una persona de un grupo mediante el centro de administración de Microsoft 365, ya no tendrá acceso a otros aspectos de colaboración, como la biblioteca de documentos de SharePoint Online, el grupo de Yammer o el compartido de OneNote. Sin embargo, seguirán teniendo acceso a la funcionalidad de chat del equipo durante aproximadamente dos horas.

Como procedimiento recomendado para administrar los miembros del equipo, puede agregarlos y quitarlos del cliente de Teams para asegurarse de que las actualizaciones de permisos para otras cargas de trabajo conectadas al grupo se realizan rápidamente. Si agrega o quita miembros del equipo fuera del cliente de Teams (mediante el centro de administración de Microsoft 365, Azure AD o Exchange Online PowerShell), los cambios pueden tardar hasta 24 horas en reflejarse en Teams.

## <a name="deleting-groups-and-teams"></a>Eliminar grupos y equipos

Si se elimina un grupo de Microsoft 365, se eliminará el alias de buzón de las conversaciones de Outlook/OWA persistentes y los invitados de reunión de Teams, y se marcará el sitio de SharePoint para su eliminación. Se tarda aproximadamente 20 minutos entre la eliminación de un equipo y su efecto en Outlook. Al eliminar un equipo del cliente de Teams, se eliminará inmediatamente de la vista a todos los miembros del equipo. Si quita miembros de un grupo de Microsoft 365 que tiene habilitada la funcionalidad de Teams, podría haber un retraso de aproximadamente dos horas antes de que el equipo se quite de la vista en el cliente de Teams para las personas afectadas que se quitaron.

Para obtener más información sobre los grupos y equipos que no tienen opciones para el final del ciclo de vida, consulte  [Opciones de fin del ciclo de vida para grupos, equipos y Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) , y [archivar o eliminar un equipo en Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).

## <a name="related-topics"></a>Temas relacionados

[Bases de Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar un grupo eliminado](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)