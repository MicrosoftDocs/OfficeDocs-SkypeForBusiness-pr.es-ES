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
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569961"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>Asignar miembros y propietarios de equipo en Microsoft Teams
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

En Microsoft Teams existen dos roles de usuario: **propietario** y **miembros**. De forma predeterminada, un usuario que crea un nuevo equipo se concede el estado de propietario. Si se crea un equipo de un grupo de 365 existente de Office, los permisos se heredan.

En la tabla siguiente muestra la diferencia de permisos entre un propietario y un miembro.


|                                   | Propietario de equipo | Miembro de equipo |
|-----------------------------------|------------|-------------|
|          **Crear equipo**          |    Sí<sup>1</sup>     |     No      |
|          **Abandonar equipo**           |    Sí     |     Sí     |
|  **Editar nombre o descripción del equipo**   |    Sí     |     No      |
|          **Eliminar equipo**          |    Sí     |     No      |
|          **Agregar canal**          |    Sí     |    Sí<sup>2</sup>|
| **Editar nombre o descripción del canal** |    Sí     |    Sí<sup>2</sup>|
|        **Eliminar canal**         |    Sí     |    Sí<sup>2</sup>|
|          **Agregar miembros**          |  Sí<sup>3</sup>   |     No hay<sup>4</sup>    |
|          **Solicitud para agregar miembros**          |  N/D   |     Sí<sup>5</sup>     |
|           **Agregar fichas**            |    Sí     |    Sí<sup>2</sup>|
|        **Agregar conectores**         |    Sí     |    Sí<sup>2</sup>|
|           **Agregar bots**            |    Sí     |    Sí<sup>2</sup>|

<sup>1</sup> los propietarios de equipo pueden crear equipos a menos que ha ha restringido de hacerlo. Vea "Permisos para crear los equipos" más adelante.
>
<sup>2</sup> estos elementos se pueden desactivar un propietario en un nivel de equipo, en cuyo caso los miembros no tienen acceso a ellos.

<sup>3</sup> después de agregar a un miembro a un equipo, un propietario también puede ascender a un miembro al estado de propietario. También es posible para un propietario disminuir el nivel de su propio estado para un miembro.

<sup>4</sup> los miembros del equipo pueden agregar a otros miembros a un equipo público.

<sup>5</sup> mientras un miembro del equipo directamente no puede agregar a miembros a un equipo privado, puede solicitar a alguien que se agregarán a un equipo que ya están miembro de. Cuando un miembro solicita a alguien que se agregarán a un equipo, los propietarios de equipo reciben una alerta que cuentan con una solicitud pendiente que se puede aceptar o rechazar.



> [!NOTE]
> Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos. Un equipo puede tener hasta 100 propietarios. Se recomienda tener al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo se evita que algunos grupos se queden huérfanos si el único propietario deja la organización. Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Permisos para crear equipos
---------------------------

De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, un equipo dentro de Microsoft Teams. Puede tener un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de nuevos grupos de Office 365 mediante la delegación de la creación del grupo y derechos de administración a un conjunto de usuarios. Para obtener instrucciones, vea [administrar quién puede crear grupos de Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Icono de Punto de decisión.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Punto de decisión         |¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?         |
| ![Icono de Siguientes pasos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Siguientes pasos         |Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.         |
