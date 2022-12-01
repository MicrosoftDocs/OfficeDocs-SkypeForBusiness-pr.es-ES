---
title: Asignar propietarios y miembros del equipo en Microsoft centro de administración de Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b25a5d654e4bd7a807918aa86e0bfd52aff2ca04
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198762"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>Asignar propietarios y miembros del equipo en Microsoft centro de administración de Teams

**Propietario** y **miembro** son los dos roles de usuario de Microsoft Teams. De forma predeterminada, se concede el estado de propietario al usuario que crea un equipo nuevo. Los propietarios y miembros tienen diferentes tipos de permisos y capacidades al interactuar con un equipo y sus canales. Consulte [Información general sobre equipos y canales en Microsoft Teams](teams-channels-overview.md) para obtener más información sobre los roles en Teams.

> [!NOTE]
> Si se crea un equipo a partir de un grupo de Microsoft 365 existente, se heredan los permisos.

## <a name="assign-a-user-role-in-teams-admin-center"></a>Asignar un rol de usuario en el Centro de administración de Teams

1. En el Centro de administración de Teams, expanda **Teams** y seleccione **Administrar equipos**.
2. Seleccione el nombre del equipo en la columna nombre para mostrar.
3. En la pestaña Miembros, puede agregar o quitar miembros y asignar roles de propietario y moderador a los miembros.

## <a name="restrict-permission-to-create-teams"></a>Restringir los permisos para crear equipos

Todos los usuarios con un buzón en Exchange Online tienen permisos para crear grupos de Microsoft 365 y un equipo en Microsoft Teams. Restrinja a los usuarios la creación de nuevos equipos y Microsoft grupos de 365 delegando los derechos de creación y administración de grupos a un conjunto de usuarios. Si esta restricción está activa, ni los propietarios ni los miembros del equipo pueden crear nuevos equipos. Si quiere más información, consulte [Administrar quién puede crear Grupos de Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

## <a name="user-permissions-based-on-assigned-roles"></a>Permisos de usuario basados en roles asignados

En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:

### <a name="teams"></a>Teams

|Tareas de Teams| Propietario de equipo | Integrante de grupo |
|---------|---------|---------|
|Crear o eliminar un equipo  |    Sí     |     No    |
|Editar nombre o descripción del equipo   |     Sí    |     No     |
|Agregar miembros a un equipo privado    |     Sí    |  No |
|Agregar miembros al equipo público    |     Sí    |     Sí   |
|Solicitud para agregar nuevo miembro   |     N/D    |    Sí   |
|Promover o disminuir nivel del estado de usuario | Sí | No |
|Abandonar equipo  |    Sí     |     Sí    |
|Agregar o quitar aplicaciones   |     Sí    |     Sí, si el propietario del equipo lo ha habilitado     |

### <a name="channels"></a>Canales

|***Tareas de canal estándar** _ | _ *Propietario del equipo** | **Miembro del equipo**|
|----|----|----|
|Crear o eliminar canal  |     Sí    |    Sí, si el propietario del equipo lo ha habilitado      |
|Editar nombre o descripción del canal    |    Sí     |     Sí, si el propietario del equipo lo ha habilitado    |
|***Tareas del canal privado***|
|Crear un canal    |    Sí     |    Sí, si el propietario del equipo lo ha habilitado      |
|Eliminar canal    |    Sí     |    No     |
|Editar nombre o descripción del canal |     No    |    N/D     |
|***Tareas de canal compartido***
|Crear un canal    |    Sí     |     No    |
|Eliminar canal | Sí | No |
|Editar nombre o descripción del canal    |    No     |     No    |
