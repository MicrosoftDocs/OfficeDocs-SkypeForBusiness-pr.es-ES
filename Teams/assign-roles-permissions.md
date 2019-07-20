---
title: Asignar miembros y propietarios de equipo en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eca4f5350e4e06d3f598191e020b8708b6f47563
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2019
ms.locfileid: "35804772"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Asignar miembros y propietarios de equipo en Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

En Microsoft Teams hay dos roles de usuario: **propietario** y **miembro**. De forma predeterminada, a un usuario que crea un equipo nuevo se le concede el estado de propietario. Además, los propietarios y miembros pueden tener capacidades de moderador para un canal (siempre que se haya configurado la moderación). Si se crea un equipo a partir de un grupo existente de Office 365, se heredan los permisos.

En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:


|                                   | Propietario de equipo | Integrante de grupo |
|-----------------------------------|------------|-------------|
|          **Crear un equipo**          |    Sí<sup>1</sup>     |     No      |
|          **Abandonar equipo**           |    Sí     |     Sí     |
|  **Editar nombre o descripción del equipo**   |    No     |     No      |
|          **Eliminar equipo**          |    No     |     No      |
|          **Agregar canal**          |    Sí     |    Sí<sup>2</sup>|
| **Editar nombre o descripción del canal** |    Sí     |    Sí<sup>2</sup>|
|        **Eliminar canal**         |    Sí     |    Sí<sup>2</sup>|
|          **Agregar miembros**          |  Sí<sup>3</sup>   |     No<sup>4</sup>    |
|          **Solicitud para agregar miembros**          |  N/D   |     Sí<sup>5</sup>     |
|           **Agregar fichas**            |    Sí     |    Sí<sup>2</sup>|
|        **Agregar conectores**         |    Sí     |    Sí<sup>2</sup>|
|           **Agregar bots**            |    Sí     |    Sí<sup>2</sup>|

<sup>1</sup> Los propietarios del equipo pueden crear equipos a no ser que se les haya quitado el permiso para hacerlo. [Permisos para crear equipos](#permissions-to-create-teams) a continuación.<br>
><sup>2</sup> un propietario puede desactivar estos elementos en el nivel del equipo, en cuyo caso los miembros no tendrían acceso a ellos.<br>
<sup>3</sup> Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado de propietario. El propietario también puede degradar su propio estado a miembro.<br>
<sup>4</sup> Los miembros del equipo pueden agregar otros miembros a un equipo público.<br>
<sup>5</sup> Aunque un miembro del equipo no puede agregar directamente miembros a un equipo privado, puede solicitar que se añada a una persona a un equipo del que ya es miembro. Cuando un miembro solicita que se añada a una persona a un equipo, los propietarios del equipo reciben una alerta de que tienen una solicitud pendiente que pueden aceptar o denegar.

> [!NOTE]
> Los propietarios pueden hacer propietarios de otros miembros en la opción **ver equipos** . Un equipo puede tener hasta 100 propietarios. Le recomendamos que tenga al menos algunos propietarios para ayudar a administrar el equipo; Esto también evitará que los grupos sean huérfanos si un propietario único abandona su organización. Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).

## <a name="moderator-capabilities"></a>Características del moderador

Además de otras funciones, los propietarios y miembros de los equipos pueden tener capacidades de moderador para un canal (siempre que la moderación esté activada para un equipo). Los moderadores pueden iniciar publicaciones nuevas en un canal y controlar si los miembros del equipo pueden responder a los mensajes de canal existentes. También pueden controlar si los bots y los conectores pueden enviar mensajes de canal.

Las capacidades del moderador se asignan en el nivel de canal. Los propietarios del equipo tienen funciones de moderador de forma predeterminada. Los miembros del equipo tienen las capacidades de moderador desactivadas de forma predeterminada, pero un propietario del equipo puede ofrecer funciones de moderador para un canal a un miembro del equipo. Los moderadores de un canal pueden agregar y quitar otros moderadores dentro de ese canal.

Para obtener más información sobre las capacidades del moderador, vea [configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

## <a name="assign-a-user-role"></a>Asignar un rol de usuario

Para asignar un rol de usuario, en Teams, seleccione el nombre del equipo y haga clic en **más opciones** > **Manage Team**. En la pestaña **miembros** , puede Agregar miembros y elegir los propietarios y moderadores (si tiene permisos suficientes). Para obtener más información, vea [cambiar la configuración del equipo en Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).

## <a name="permissions-to-create-teams"></a>Permisos para crear equipos

De manera predeterminada, todos los usuarios que tengan un buzón de correo en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, para crear equipos dentro de Microsoft Teams. Puede ejercer un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de grupos de Office 365 si delega la creación de grupos y los derechos de administración en un conjunto de usuarios. Para ver más información, consulte [Administrar quién puede crear Grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Un icono que representa un punto de decisión](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Punto de decisión         |¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?         |
| ![Un icono que representa los pasos siguientes](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Siguientes pasos         |Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.         |
