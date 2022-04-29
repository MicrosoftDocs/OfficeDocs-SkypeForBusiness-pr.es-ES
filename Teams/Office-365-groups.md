---
title: Grupos de Microsoft 365 y Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo funcionan Microsoft 365 grupos y pertenencias a grupos con Microsoft Teams.
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125435"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Grupos de Microsoft 365 y Microsoft Teams

Grupos de Microsoft 365 es el servicio de pertenencia a aplicaciones cruzadas de Microsoft 365. En un nivel básico, un grupo de Microsoft 365 es un objeto de Azure Active Directory con una lista de miembros y un acoplamiento con cargas de trabajo relacionadas, incluidos un sitio de grupo SharePoint, un buzón de Exchange compartido, Planner y OneNote bloc de notas. Puede agregar o quitar personas al grupo como lo haría con cualquier otro objeto de seguridad basado en grupo en Active Directory.

![Diagrama que muestra Grupos de Microsoft 365 y servicios relacionados.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

De forma predeterminada, los usuarios de Microsoft 365 pueden crear y administrar grupos. Para obtener más información sobre Grupos de Microsoft 365, vea [Obtener información sobre Grupos de Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) y el póster [Grupos en Microsoft 365 para arquitectos de TI](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

## <a name="how-microsoft-365-groups-work-with-teams"></a>Cómo Grupos de Microsoft 365 trabajar con Teams

Al crear un equipo, se crea un grupo de Microsoft 365 para administrar la pertenencia al equipo. Los servicios relacionados del grupo, como un sitio de SharePoint, un buzón, etc., se crean al mismo tiempo.

Las personas que crean equipos pueden elegir usar un grupo de Microsoft 365 existente si son propietarios de ese grupo. Cada canal del equipo tiene una carpeta independiente en la biblioteca de documentos. La creación de carpetas directamente en la biblioteca de documentos no crea canales en el equipo.

Al crear un grupo de Microsoft 365 en Outlook o SharePoint, el buzón del grupo es visible en Outlook. Al crear un equipo en Teams, el buzón de grupo se oculta de forma predeterminada. Puede usar el cmdlet [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) con el parámetro **HiddenFromExchangeClientsEnabled** para que un buzón sea visible.

## <a name="group-membership"></a>Pertenencia a grupos

Si quita a un miembro de un equipo, también se quitará del grupo de Microsoft 365. La eliminación del grupo quita inmediatamente el equipo y los canales del cliente de Teams. Si quita a una persona de un grupo con la Centro de administración de Microsoft 365, ya no tendrá acceso a otros aspectos de colaboración, como SharePoint biblioteca de documentos en línea, Yammer grupo o OneNote compartidos. Sin embargo, seguirán teniendo acceso a la funcionalidad de chat del equipo durante aproximadamente dos horas.

Como procedimiento recomendado para administrar miembros del equipo, agréguelos y quítelos del cliente de Teams para asegurarse de que las actualizaciones de permisos para otras cargas de trabajo conectadas a grupos se produzcan rápidamente. Si agrega o quita miembros del equipo fuera del cliente de Teams (mediante el Centro de administración de Microsoft 365, Azure AD o Exchange Online PowerShell), los cambios pueden tardar hasta 24 horas en reflejarse en Teams.

## <a name="deleting-groups-and-teams"></a>Eliminar grupos y equipos

Al eliminar un grupo de Microsoft 365, se quitará el alias del buzón para las conversaciones persistentes de Outlook/OWA y Teams invitaciones a reuniones, y se marcará el sitio SharePoint para su eliminación. Se tarda aproximadamente 20 minutos entre la eliminación de un equipo y su efecto en Outlook. Al eliminar un equipo del cliente de Teams, se quitará inmediatamente de la vista a todos los miembros del equipo. Si quita miembros de un grupo de Microsoft 365 que tiene habilitada Teams funcionalidad, puede haber un retraso de aproximadamente dos horas antes de quitar el equipo de la vista en el cliente de Teams para las personas afectadas que se quitaron.

Para obtener más información sobre las opciones de fin de ciclo de vida de los grupos y equipos, consulte [Opciones de fin de ciclo de vida para grupos, equipos y Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) y [Archivar o eliminar un equipo en Microsoft Teams](./archive-or-delete-a-team.md).

## <a name="related-topics"></a>Temas relacionados

[Fundaciones de Microsoft Teams (vídeo)](https://aka.ms/teams-foundations)

[Restaurar un grupo eliminado](/microsoft-365/admin/create-groups/restore-deleted-group)
