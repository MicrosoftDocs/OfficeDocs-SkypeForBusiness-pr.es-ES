---
title: Asignar miembros y propietarios de equipo en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
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
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493805"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Asignar miembros y propietarios de equipo en Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Dentro de Microsoft Teams hay dos roles: **Propietario** y **Miembro**. De forma predeterminada, el usuario que crea un equipo tiene el estado Propietario. Si se crea un equipo a partir de un grupo de Office 365 existente, los permisos se heredan.

En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:


|                                   | Propietario de equipo | Integrante de grupo |
|-----------------------------------|------------|-------------|
|          **Crear un equipo**          |    Sí<sup>1</sup>     |     No      |
|          **Abandonar equipo**           |    Sí     |     Sí     |
|  **Editar nombre o descripción del equipo**   |    Sí     |     No      |
|          **Eliminar equipo**          |    Sí     |     No      |
|          **Agregar canal**          |    Sí     |    Sí<sup>2</sup>|
| **Editar nombre o descripción del canal** |    Sí     |    Sí<sup>2</sup>|
|        **Eliminar canal**         |    Sí     |    Sí<sup>2</sup>|
|          **Agregar miembros**          |  Sí<sup>3</sup>   |     No<sup>4</sup>    |
|          **Solicitud para agregar miembros**          |  N/D   |     Sí<sup>5</sup>     |
|           **Agregar fichas**            |    Sí     |    Sí<sup>2</sup>|
|        **Agregar conectores**         |    Sí     |    Sí<sup>2</sup>|
|           **Agregar bots**            |    Sí     |    Sí<sup>2</sup>|

<sup>1</sup> Los propietarios del equipo pueden crear equipos a no ser que se les haya quitado el permiso para hacerlo. Consulte "Permisos para crear equipos" más abajo.
>
<sup>2</sup> Un propietario puede desactivar estos elementos a nivel de equipo, en cuyo caso, los miembros no tendrían acceso a ellos.

<sup>3</sup> Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado de propietario. El propietario también puede degradar su propio estado a miembro.

<sup>4</sup> Los miembros del equipo pueden agregar otros miembros a un equipo público.

<sup>5</sup> Aunque un miembro del equipo no puede agregar directamente miembros a un equipo privado, puede solicitar que se añada a una persona a un equipo del que ya es miembro. Cuando un miembro solicita que se añada a una persona a un equipo, los propietarios del equipo reciben una alerta de que tienen una solicitud pendiente que pueden aceptar o denegar.



> [!NOTE]
> Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos. Un equipo puede tener hasta 100 propietarios. Se recomienda tener al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo se evita que algunos grupos se queden huérfanos si el único propietario deja la organización. Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Permisos para crear equipos
---------------------------

De manera predeterminada, todos los usuarios que tengan un buzón de correo en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, para crear equipos dentro de Microsoft Teams. Puede ejercer un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de grupos de Office 365 si delega la creación de grupos y los derechos de administración en un conjunto de usuarios. Para ver más información, consulte [Administrar quién puede crear Grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Un icono que representa un punto de decisión](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Punto de decisión         |¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?         |
| ![Un icono que representa los pasos siguientes](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Siguientes pasos         |Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.         |
