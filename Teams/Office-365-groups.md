---
title: Office 365 grupos y Microsoft Teams
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: Aprenda cómo funcionan los grupos y las pertenencias a grupos de Office 365 con Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9734404e767e9769a44a09fa7afe22bf251e4ba7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245171"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 grupos y Microsoft Teams
=====================================

> [!Tip]
> Vea la siguiente sesión para obtener información sobre cómo Teams interactúa con Azure Active Directory (Azure AD), Office 365 Groups, Exchange, SharePoint y OneDrive para la empresa: [bases de Microsoft Teams](https://aka.ms/teams-foundations)

Office 365 Groups es el servicio de suscripción entre aplicaciones de Office 365. En el nivel básico, un grupo de Office 365 es un objeto de Azure Active Directory con una lista de miembros y un acoplamiento flexible a las cargas de trabajo relacionadas, como un sitio de grupo de SharePoint, un grupo de Yammer, recursos compartidos de buzón de Exchange, Planner, Power BI y OneNote. Puede Agregar o quitar personas del grupo de la misma manera que cualquier otro objeto de seguridad basado en grupos en Active Directory.

Un administrador de Office 365 puede definir un grupo de Office 365, agregar miembros y beneficiarse de características como un buzón compartido de Exchange, una biblioteca de documentos de SharePoint, un grupo de Yammer, etc. Para obtener más información sobre los grupos de Office 365, vea [más información sobre los grupos de office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

No se pierda los [grupos de pósters de Microsoft 365 para arquitectos de ti](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-office-365-groups-work"></a>Cómo funcionan los grupos de Office 365
--------------------------

Al crear un equipo, en el back-end, está creando un grupo de Office 365 y la biblioteca de documentos de SharePoint asociada y el Bloc de notas de OneNote, junto con los vínculos a otras aplicaciones de nube de Office 365. Si la persona que crea el equipo es propietaria de un grupo existente de Office 365 público o privado, puede Agregar la funcionalidad de Teams al grupo si tiene menos de 5000 usuarios y nunca se ha agregado a teams. Esto crea un canal **General** predeterminado en el que residen los mensajes de chat, documentos, OneNote y otros objetos. Si visualiza la biblioteca de documentos para el canal, se mostrará la carpeta **General** que representa el canal en el equipo. Y lo que es más importante, si crea su propia estructura de carpetas dentro de una biblioteca de documentos, **no se propaga** a teams como un canal; por ahora, solo fluye de Teams a SharePoint.

> [!NOTE]
> En función de los comentarios de los clientes, los nuevos grupos de Office 365 generados como resultado de la creación de un equipo en Microsoft Teams ya no se mostrarán en Outlook de forma predeterminada. Para los clientes que desean continuar con el comportamiento existente de mostrar estos grupos en Outlook, se proporcionará un cmdlet de PowerShell de Exchange online que puede habilitar el grupo para la experiencia de Outlook. Los grupos creados a través de Outlook y, posteriormente, habilitados para equipos, seguirán apareciendo en Outlook y en Teams. Esta actualización se implementará gradualmente en Outlook y Teams en los próximos meses.

> [!NOTE]
> Si se elimina un grupo de Office 365, se eliminará el alias de buzón de las conversaciones de Outlook/OWA persistentes y los invitados de reunión de Teams y se marcará el sitio de SharePoint para su eliminación. Se tarda aproximadamente 20 minutos entre la eliminación de un equipo y su efecto en Outlook. Al eliminar un equipo del cliente de Teams, se eliminará inmediatamente de la vista a todos los miembros del equipo. Si quita miembros de un grupo de Office 365 que tiene habilitada la funcionalidad de Teams, podría haber un retraso de aproximadamente dos horas antes de que se elimine el equipo de la vista en el cliente de Teams para las personas afectadas que se quitaron.
>
>Lea [esto](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) para obtener información sobre cómo restaurar un grupo de Office 365 que ha eliminado.

<a name="group-membership"></a>Pertenencia a grupos
----------------

Las características y capacidades de grupo para los usuarios dependen de la ubicación de la pertenencia a grupos. Por ejemplo, si quita un miembro de un equipo, se elimina también del grupo de Office 365. La eliminación del grupo elimina el equipo y los canales inmediatamente del cliente de Teams. Si quita una persona de un grupo mediante el centro de administración de Microsoft 365, ya no tendrá acceso a otros aspectos de colaboración, como la biblioteca de documentos de SharePoint Online, el grupo de Yammer o el compartido de OneNote. Sin embargo, seguirán teniendo acceso a la funcionalidad de chat del equipo durante aproximadamente dos horas.

Como procedimiento recomendado para administrar miembros de equipos, agregue y quite miembros del cliente de Teams para asegurarse de que se aplica el control de acceso en cascada correcto a otras aplicaciones de nube dependientes. Además, evitará que una experiencia desligada deje a las personas con la impresión de que todavía tienen acceso a los recursos que usaron (hasta el próximo ciclo de sincronización agrega o revoca el acceso a un componente particular del servicio). Si agrega o quita miembros del equipo fuera del cliente de Teams (mediante el centro de administración de Microsoft 365, Azure AD o Exchange Online PowerShell), los cambios pueden tardar hasta dos horas en reflejarse en Teams.
