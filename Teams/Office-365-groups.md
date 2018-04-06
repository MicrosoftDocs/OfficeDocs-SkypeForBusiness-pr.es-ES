---
title: Grupos de Office 365 y Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Aprenda cómo funcionan los grupos y las pertenencias a grupos de Office 365 con Microsoft Teams.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2018
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

Características de los grupos y las capacidades de los usuarios depende donde usted maneja la pertenencia a un grupo de. Por ejemplo, si quita a un miembro de un equipo, se quitan del grupo de 365 de Office. Eliminación del grupo inmediatamente quita el equipo y los canales desde el cliente de los equipos. Si quita a una persona de un grupo mediante el portal de administración de Office 365, ya no tendrán acceso a los otros aspectos de colaboración como biblioteca de documentos SharePoint Online, grupo Yammer o compartida OneNote. Sin embargo, aún tendrán acceso a la funcionalidad de chat del equipo durante una hora aproximadamente.

Mejores prácticas para administrar los miembros de los equipos: agregar y quitar miembros desde el cliente de los equipos para asegurar el correcto control de acceso en cascada a otras aplicaciones de nube dependientes se aplica. Además, evitará una experiencia inconexa dejando la gente con la impresión aún tienen acceso a los recursos que se solía (hasta que se agrega el siguiente ciclo de sincronización o revoca el acceso a un componente concreto del servicio). Si agrega o quita los miembros del equipo fuera el cliente de los equipos (utilizando Office 365 Admin Center, AD Azure, o PowerShell en línea de Exchange), que a veces tarda hasta una hora para que los cambios se reflejen en los equipos.
