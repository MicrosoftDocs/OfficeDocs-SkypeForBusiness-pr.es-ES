---
title: Grupos de Office 365 y Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Aprenda cómo funcionan los grupos y las pertenencias a grupos de Office 365 con Microsoft Teams.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e77a91f1859c6d227801de2f31dbe2855ea30a2e
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "18999146"
---
<a name="office-365-groups-and-microsoft-teams"></a>Grupos de Office 365 y Microsoft Teams
=====================================

Grupos de Office 365 es el servicio de pertenencia multiplataforma en Office 365. En el nivel básico, Grupos de Office 365 es un objeto en Azure Active Directory con una lista de miembros y un acoplamiento débil a cargas de trabajo relacionadas, incluido el sitio de equipo de SharePoint, Yammer Group, los recursos de buzón de Exchange compartidos, Planner, PowerBI y OneNote. Puede agregar o quitar personas del grupo del mismo modo que con cualquier otro objeto de seguridad basado en grupo en Active Directory.

Un administrador de Office 365 puede definir un grupo de Office 365, agregar miembros y aprovechar características como el buzón compartido de Exchange, la biblioteca de documentos de SharePoint, Yammer Group, etc. Para más información sobre Office 365 Groups, visite: [Obtenga más información sobre los grupos de Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Funcionamiento de Grupos de Office 365 
--------------------------

Cuando crea un equipo de Microsoft Teams, en el back-end se crea un Grupo de Office 365 junto con la biblioteca de documentos de SharePoint asociada, el bloc de notas de OneNote junto con valores equivalentes en otras aplicaciones en la nube de Office 365. Si la persona que crea el equipo es propietario de un grupo privado o público de Office 365 existente, puede agregar la funcionalidad de Microsoft Teams al grupo. De este modo se crea un canal “General” en el que residen los mensajes de chat, los documentos, OneNote y otros objetos. En la biblioteca de documentos del canal se puede ver la carpeta “General” que representa en canal en el equipo. Es importante recordar que si crea su propia estructura de carpetas dentro de una biblioteca de documentos, **no se propaga** a Microsoft Teams como un canal. Por el momento, solo fluye de Microsoft Teams a SharePoint.




> [!NOTE]
> Si se elimina un grupo de Office 365, se eliminará el alias de buzón para las conversaciones persistentes de Outlook/OWA e invitaciones a reuniones de Microsoft Teams, y el sitio de SharePoint se marcará para su eliminación. Solo se tarda 20 minutos aproximadamente desde que se elimina un equipo y se aprecia su efecto en Outlook. Si se elimina un equipo del cliente de Microsoft Teams, se eliminará inmediatamente de la vista a todos los que sean miembros del equipo. Si quita un miembro de un grupo de Office 365 que ha tenido habilitada la funcionalidad de Microsoft Teams, podría haber un retraso de aproximadamente una hora antes de que el equipo se elimine de la vista en el cliente de Microsoft Teams para las personas afectadas que se hayan eliminado.

<a name="group-membership"></a>Pertenencia a grupos
----------------

Grupo características y funciones para los usuarios depende donde unidad pertenencia al grupo desde. Por ejemplo, si quita a un miembro de un equipo, se quitan del grupo así como Office 365. Eliminación del grupo inmediatamente quita el equipo y canales desde el cliente de los equipos. Si quita a una persona de un grupo mediante el portal de administración de Office 365, ya no tendrán acceso a los otros aspectos de colaboración como biblioteca de documentos SharePoint Online, grupo de Yammer o compartida OneNote. Sin embargo, aún tendrán acceso a la funcionalidad de chat del equipo durante aproximadamente una hora.

Práctica recomendada para la administración de los miembros de los equipos: agregar y quitar miembros desde el cliente de los equipos para asegurarse de que se aplica el control de acceso en cascada correcta a otras aplicaciones dependientes en la nube. Además, evitará un personas salir disjuntos experiencia con la impresión aún tienen acceso a los recursos que se solía (hasta que el próximo ciclo de sincronización agrega o revoca el acceso a un componente concreto del servicio). Si agrega o quita los integrantes del grupo fuera el cliente de los equipos (mediante el uso de centro de administración de Office 365, Azure AD o Exchange Online PowerShell), que a veces tarda hasta una hora para que los cambios se reflejan en los equipos.
