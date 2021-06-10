---
title: Microsoft 365 Grupos y Microsoft Teams
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
description: Obtenga información sobre cómo Microsoft 365 grupos y pertenencias a grupos funcionan con Microsoft Teams.
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105246"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Grupos y Microsoft Teams

Microsoft 365 Grupos es el servicio de pertenencia a aplicaciones cruzadas en Microsoft 365. En un nivel básico, un grupo de Microsoft 365 es un objeto de Azure Active Directory con una lista de miembros y un acoplamiento a cargas de trabajo relacionadas, incluido un sitio de grupo de SharePoint, un buzón de Exchange compartido, Planner y Power BI área de trabajo. Puede agregar o quitar personas al grupo del mismo modo que lo haría con cualquier otro objeto de seguridad basado en grupos en Active Directory.

![Diagrama que muestra Microsoft 365 grupos y servicios relacionados](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

De forma predeterminada, los usuarios de Microsoft 365 pueden crear y administrar grupos. Para obtener más información sobre Microsoft 365, vea Información sobre Microsoft 365 [grupos](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) y los grupos de Microsoft 365 para el póster [arquitectos de](teams-architecture-solutions-posters.md#groups-in-microsoft-365) TI.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Cómo Microsoft 365 los grupos de Teams

Al crear un equipo, se crea Microsoft 365 grupo para administrar la pertenencia al equipo. Los servicios relacionados del grupo, como un SharePoint, Power BI área de trabajo, etc. se crean al mismo tiempo.

Las personas que crean equipos pueden elegir usar un grupo de Microsoft 365 existente si son propietarios de ese grupo. Cada canal del equipo tiene una carpeta independiente en la biblioteca de documentos. La creación de carpetas directamente en la biblioteca de documentos no crea canales en el equipo.

Al crear un grupo Microsoft 365 en Outlook o SharePoint, el buzón del grupo está visible en Outlook. Al crear un equipo en Teams, el buzón de grupo está oculto de forma predeterminada. Puede usar el cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) con el parámetro **HiddenFromExchangeClientsEnabled** para hacer visible un buzón.

## <a name="group-membership"></a>Pertenencia a grupos

Si quita un miembro de un equipo, también se quitarán del Microsoft 365 grupo. La eliminación del grupo quita inmediatamente el equipo y los canales del Teams cliente. Si quita a una persona de un grupo con el Centro de administración de Microsoft 365, ya no tendrá acceso a los demás aspectos de colaboración, como la biblioteca de documentos en línea de SharePoint, el grupo Yammer o el OneNote. Sin embargo, seguirán teniendo acceso a la funcionalidad de chat del equipo durante aproximadamente dos horas.

Como procedimiento recomendado para administrar miembros del equipo, agrégrelos y quítelos del cliente de Teams para asegurarse de que las actualizaciones de permisos para otras cargas de trabajo conectadas a grupos se produzcan rápidamente. Si agrega o quita miembros del equipo fuera del cliente de Teams (mediante el Centro de administración de Microsoft 365, Azure AD o Exchange Online PowerShell), los cambios pueden tardar hasta 24 horas en reflejarse en Teams.

## <a name="deleting-groups-and-teams"></a>Eliminar grupos y equipos

Al eliminar un grupo de Microsoft 365, se quitará el alias del buzón para las conversaciones Outlook/OWA persistentes y las invitaciones Teams reunión y se marcará el sitio SharePoint para su eliminación. Se tarda aproximadamente 20 minutos entre la eliminación de un equipo y su efecto en Outlook. Al eliminar un equipo del Teams cliente, se quitará inmediatamente de la vista a todos los miembros del equipo. Si quita miembros de un grupo de Microsoft 365 que tiene habilitada una funcionalidad Teams, podría haber un retraso de aproximadamente dos horas antes de que el equipo se quite de la vista en el cliente de Teams para las personas afectadas que se quitaron.

Para obtener más información sobre las opciones de fin de ciclo de vida de grupos y equipos, vea Opciones de fin de ciclo de vida para [grupos,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) equipos y Yammer y Archivar o eliminar un [equipo en Microsoft Teams](./archive-or-delete-a-team.md).

## <a name="related-topics"></a>Temas relacionados

[Fundamentos de Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar un grupo eliminado](/microsoft-365/admin/create-groups/restore-deleted-group)