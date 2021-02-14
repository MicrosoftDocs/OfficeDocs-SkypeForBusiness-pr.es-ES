---
title: Información general sobre la pertenencia dinámica para los equipos
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo Microsoft Teams admite equipos asociados con grupos de Microsoft 365 mediante la pertenencia dinámica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583929"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Información general sobre la pertenencia dinámica para los equipos

Microsoft Teams admite equipos asociados con grupos de Microsoft 365 mediante *la pertenencia dinámica.* La pertenencia dinámica permite que la pertenencia a un equipo se defina mediante una o más reglas que comprueban determinados atributos de usuario en Azure Active Directory (Azure AD). Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que cambian los atributos de usuario o los usuarios se unen y abandonan el espacio empresarial.

Con la pertenencia dinámica, puede configurar equipos para ciertos grupos de usuarios de su organización. Entre los posibles escenarios se incluyen:
- Un hospital puede crear distintos equipos para enfermeras, médicos y facultativos para difundir las comunicaciones. Esto es especialmente importante si el hospital depende de empleados temp.
- Una universidad puede crear un equipo para todos los profesores de un instituto en particular, incluidos los profesores adjuntos que cambian con frecuencia.
- Una línea aérea quiere crear un equipo para cada vuelo (por ejemplo, un martes por la tarde sin parar desde Chicago a Atlanta) y tener asignados o quitados de forma automática un equipo de pilotos que cambia con frecuencia según sea necesario.

Con esta característica, los miembros de un equipo determinado se actualizan automáticamente en función de un conjunto específico de criterios, en lugar de administrar manualmente la pertenencia. Para ello, es necesario asignar licencias de Azure AD Premium P1 y la pertenencia a equipos por parte de un administrador de inquilinos [a](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) cualquier propiedad de Azure AD del usuario, siempre que tenga un inquilino y una cuenta de administrador.

Microsoft Teams puede tardar entre unos minutos y dos horas en reflejar los cambios dinámicos de pertenencia una vez que se han hecho efectivos en el grupo de Microsoft 365 de un equipo.

> [!NOTE]
> - Las reglas pueden definir quién es un miembro del equipo, pero no quién es propietario del equipo.
> - Consulte [los límites y las especificaciones de Microsoft Teams para ver](limits-specifications-teams.md) los límites actuales de los tamaños de los equipos y canales.
> - Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas de grupo dinámicos.
> -    Los miembros no podrán dejar equipos con el apoyo de grupos dinámicos.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Crear y administrar un grupo de Microsoft 365 con pertenencia dinámica

Una vez que haya iniciado sesión como administrador de inquilinos, siga las instrucciones de [Crear un grupo dinámico y compruebe el estado.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) Si es necesario, consulte reglas [de pertenencia dinámica para grupos de Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Crear un equipo nuevo con el grupo de Microsoft 365

Ahora deje tiempo para que los cambios de pertenencia se a efecto y cree un equipo nuevo como se describe en Crear un equipo [a partir de un grupo existente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar pertenencia dinámica a un equipo existente

También puede elegir un equipo existente y cambiarlo para que tenga una pertenencia dinámica, como se describe en Cambiar la pertenencia a grupos estáticos a dinámico [en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>Cambios en el comportamiento del cliente

Una vez habilitada la pertenencia dinámica para un equipo, los clientes de Teams ya no permitirán la administración de miembros para el equipo. Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de unión y abandonar el equipo están ocultas.
