---
title: Asignar miembros y propietarios de equipo en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b574c04acdf466f2ad8a46401dd347ff2a82b876eaa61815d0d3ea07d7d9cb8b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331102"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams"></a>Asignar miembros y propietarios de equipo en Microsoft Teams

En Microsoft Teams hay dos roles de usuario: **propietario** y **miembro**. De forma predeterminada, el usuario que crea un equipo nuevo recibe el estado de propietario. Además, los propietarios y los miembros del equipo pueden tener funciones de moderador para un canal (según la moderación que se configure). Si un equipo se crea a partir de un grupo existentede Microsoft 365, los permisos se heredan.

En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:


|    Tarea                               | Propietario de equipo | Integrante de grupo |
|-----------------------------------|------------|-------------|
|          **Crear un equipo**          |    Sí<sup>1</sup>     |     No      |
|          **Abandonar equipo**           |    Sí     |     Sí     |
|  **Editar nombre o descripción del equipo**   |    Sí     |     No      |
|          **Eliminar equipo**          |    Sí     |     No      |
|          **Añadir un canal estándar**          |    Sí     |    Sí<sup>2</sup>|
| **Editar el nombre o la descripción del canal estándar** |    Sí     |    Sí<sup>2</sup>|
|        **Eliminar canal estándar**         |    Sí     |    Sí<sup>2</sup>|
|          ***Añadir un canal privado**          |    Sí     |    Sí<sup>2</sup>|
| ***Editar el nombre o la descripción del canal privado** |    No     |    N/D|
|        ***Eliminar canal privado**         |    Sí     |    No|
|          **Agregar miembros**          |  Sí<sup>3</sup>   |     No<sup>4</sup>    |
|          **Solicitud para agregar miembros**          |  N/D   |     Sí<sup>5</sup>     |
|           **Agregar aplicaciones**            |    Sí     |    Sí<sup>2</sup>|

<sup>1</sup> Los propietarios del equipo pueden crear equipos a no ser que se les haya quitado el permiso para hacerlo. [Permisos para crear equipos](#permissions-to-create-teams):<br>
<sup>2</sup> Un propietario puede desactivar estos elementos a nivel de equipo, en cuyo caso, los miembros no tendrían acceso a ellos.<br>
<sup>3</sup> Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado de propietario. El propietario también puede degradar su propio estado a miembro.<br>
<sup>4</sup> Los miembros del equipo pueden agregar otros miembros a un equipo público.<br>
<sup>5</sup> Aunque un miembro del equipo no puede agregar directamente miembros a un equipo privado, puede solicitar que se añada a una persona a un equipo del que ya es miembro. Cuando un miembro solicita que se añada a una persona a un equipo, los propietarios del equipo reciben una alerta de que tienen una solicitud pendiente que pueden aceptar o denegar.

*Para obtener más información sobre los permisos para los canales privados, consulte [Canales privados en Teams](private-channels.md).

> [!NOTE]
> Los propietarios pueden establecer a otros miembros como propietarios en la opción **Ver equipos**. Un equipo puede tener hasta 100 propietarios. Le recomendamos que tenga al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo evitará que algunos grupos se queden huérfanos si el único propietario deja la organización. Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Capacidades del moderador

Entre otras, tanto los propietarios como los miembros de un equipo pueden tener capacidades de moderador para un canal (según si la moderación de un equipo está activada). Los moderadores pueden iniciar nuevas publicaciones en un canal y controlar si los miembros del equipo pueden responder a los mensajes del canal existentes. También pueden controlar si los bots y los conectores pueden enviar mensajes de canal.

Las capacidades de moderador se asignan en el nivel de canal. De forma predeterminada, los propietarios de un equipo tienen capacidades de moderador. Los miembros de un equipo tienen las capacidades de moderador desactivadas de forma predeterminada, pero el propietario puede asignar capacidades de moderador para un canal a un miembro del equipo. Los moderadores de un canal pueden agregar y quitar moderadores a ese canal.

Para obtener más información sobre las capacidades del moderador, consulte[Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Asignar un rol de usuario

Para asignar un rol de usuario, en Teams, seleccione el nombre del equipo y clique en **Más opciones** > **Administrar equipo**. En la pestaña **Miembros**, puede agregar miembros y elegir los propietarios y los moderadores (si tiene los permisos suficientes). Para obtener más información, consulte [Cambiar la configuración de equipo en Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

## <a name="permissions-to-create-teams"></a>Permisos para crear equipos

De manera predeterminada, todos los usuarios que tengan un buzón de correo en Exchange Online tienen permisos para crear grupos de Microsoft 365 y, por lo tanto, para crear equipos dentro de Microsoft Teams. Puede ejercer un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de grupos de Microsoft 365 si delega la creación de grupos y los derechos de administración en un conjunto de usuarios. Para ver más información, consulte [Administrar quién puede crear Grupos de Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).
