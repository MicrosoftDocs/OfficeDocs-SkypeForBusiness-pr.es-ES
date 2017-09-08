---
title: "Office 365 y Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: overview
ms.prod: teams
description: "Aprenda cómo funcionan los grupos y las pertenencias a grupos de Office 365 con Microsoft Teams."
ms.openlocfilehash: d2a0f9c4d12a1c2e92f552b0293610d5d0ecadc9
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2017
---
<a name="office-365-groups-and-microsoft-teams"></a>Grupos de Office 365 y Microsoft Teams
=====================================

Grupos de Office 365 es el servicio de pertenencia multiplataforma en Office 365. En el nivel básico, Grupos de Office 365 es un objeto en Azure Active Directory con una lista de miembros y un acoplamiento débil a cargas de trabajo relacionadas, incluido el sitio de equipo de SharePoint, Yammer Group, los recursos de buzón de Exchange compartidos, Planner, PowerBI y OneNote. Puede agregar o quitar personas del grupo del mismo modo que con cualquier otro objeto de seguridad basado en grupo en Active Directory.

Un administrador de Office 365 puede definir un grupo de Office 365, agregar miembros y aprovechar características como el buzón compartido de Exchange, la biblioteca de documentos de SharePoint, Yammer Group, etc. Para más información sobre Office 365 Groups, visite: [Obtenga más información sobre los grupos de Office 365](https://support.office.com/en-us/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Funcionamiento de Grupos de Office 365 
--------------------------

Cuando crea un equipo de Microsoft Teams, en el back-end se crea un Grupo de Office 365 junto con la biblioteca de documentos de SharePoint asociada, el bloc de notas de OneNote junto con valores equivalentes en otras aplicaciones en la nube de Office 365. Si la persona que crea el equipo es propietario de un grupo privado o público de Office 365 existente, puede agregar la funcionalidad de Microsoft Teams al grupo. De este modo se crea un canal “General” en el que residen los mensajes de chat, los documentos, OneNote y otros objetos. En la biblioteca de documentos del canal se puede ver la carpeta “General” que representa en canal en el equipo. Es importante recordar que si crea su propia estructura de carpetas dentro de una biblioteca de documentos, **no se propaga** a Microsoft Teams como un canal. Por el momento, solo fluye de Microsoft Teams a SharePoint.

|||
|---------|---------|
|  ![](media/Understand_Office_365_groups_and_Microsoft_Teams_image1.png) Nota    |Si se elimina un grupo de Office 365, se eliminará el alias de buzón para las conversaciones persistentes de Outlook/OWA e invitaciones a reuniones de Microsoft Teams, y el sitio de SharePoint se marcará para su eliminación. Solo se tarda 20 minutos aproximadamente desde que se elimina un equipo y se aprecia su efecto en Outlook. Si se elimina un equipo del cliente de Microsoft Teams, se eliminará inmediatamente de la vista a todos los que sean miembros del equipo. Si quita un miembro de un grupo de Office 365 que ha tenido habilitada la funcionalidad de Microsoft Teams, podría haber un retraso de aproximadamente una hora antes de que el equipo se elimine de la vista en el cliente de Microsoft Teams para las personas afectadas que se hayan eliminado.         |


<a name="group-membership"></a>Pertenencia a grupos
----------------

En función de dónde proceda la pertenencia a grupos, las características y las capacidades que tendrán los usuarios serán distintas. Por ejemplo, si quita un miembro de un equipo, se quitará también del grupo de Office 365. Al eliminarlo del grupo, se elimina inmediatamente del equipo y los canales del cliente de Microsoft Teams. Si quita una persona de un grupo a través del portal de administración de Office 365, ya no tendrá acceso a otros aspectos de colaboración, como la biblioteca de documentos de SharePoint Online, Yammer Group o OneNote compartido. Sin embargo, seguirá teniendo acceso a la funcionalidad de chat del equipo durante una hora aproximadamente.

Nuestra recomendación con respecto a la administración de miembros de Microsoft Teams es la de agregar o eliminar funcionalidades a través del cliente de Microsoft Teams para garantizar que se aplica el correcto control de acceso en cascada a otras aplicaciones de nube dependientes. Además, así evitará una experiencia fraccionada, ya que los usuarios tendrán la impresión de que siguen teniendo acceso a los recursos que solían tener (hasta que en el siguiente ciclo de sincronización se agregue o se revoque el acceso a un determinado componente del servicio).
