---
title: Asignar roles y permisos en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b6dfc74b3d7dc740cc970f711f32fac1d75e2d5
ms.sourcegitcommit: c18710a46018fe4c1d0ceb99710f18bbc25aad54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2018
ms.locfileid: "19441664"
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>Asignar roles y permisos en Microsoft Teams
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Dentro de Microsoft Teams hay dos roles: **Propietario** y **Miembro**. De forma predeterminada, el usuario que crea un equipo tiene el estado Propietario. Si se crea un equipo a partir de un grupo de Office 365 existente, los permisos se heredan.

En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:

|  |Propietario de equipo  |Miembro de equipo  |
|---------|---------|---------|
|**Crear equipo**     |Sí        |No         |
|**Abandonar equipo**     |Sí         |Sí         |
|**Editar nombre o descripción del equipo**      |Sí         |No         |
|**Eliminar equipo**      |Sí         |No         |
|**Agregar canal**      |Sí         |Sí*         |
|**Editar nombre o descripción del canal**      |Sí         |Sí*         |
|**Eliminar canal**      |Sí         |Sí*         |
|**Agregar miembros**      |Sí         |No         |
|**Agregar fichas**      |Sí         |Sí*         |
|**Agregar conectores**      |Sí         |Sí*         |
|**Agregar bots**      |Sí         |Sí*         |
\* Un propietario puede desactivar estos elementos a nivel de equipo, en cuyo caso, los miembros no tendrían acceso a ellos.

\*\*Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado Propietario. También es posible que un propietario disminuya su propio estado a Miembro.



> [!NOTE]
> Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos. Un equipo puede tener hasta 100 propietarios. Se recomienda tener al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo se evita que algunos grupos se queden huérfanos si el único propietario deja la organización. Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Permisos para crear equipos
---------------------------

De forma predeterminada, todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, un equipo dentro de Microsoft Teams. Puede tener un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de nuevos grupos de Office 365 mediante la delegación de la creación del grupo y derechos de administración a un conjunto de usuarios. Para obtener instrucciones, vea [administrar quién puede crear grupos de Office 365](https://support.office.com/en-us/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).


||||
|---------|---------|---------|
| ![Icono de Punto de decisión.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Punto de decisión         |¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?         |
| ![Icono de Siguientes pasos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Siguientes pasos         |Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.         |
