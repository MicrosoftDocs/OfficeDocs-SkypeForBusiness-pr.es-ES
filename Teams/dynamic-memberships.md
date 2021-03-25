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
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120772"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Información general sobre la pertenencia dinámica para los equipos

Microsoft Teams admite equipos asociados con grupos de Microsoft 365 mediante la *pertenencia dinámica.* La pertenencia dinámica permite definir la pertenencia a un equipo mediante una o más reglas que comprueban si hay determinados atributos de usuario en Azure Active Directory (Azure AD). Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que cambian los atributos de usuario o los usuarios se unen y abandonan el espacio empresarial.

Con la pertenencia dinámica, puede configurar equipos para determinadas cohortes de usuarios de su organización. Entre los posibles escenarios se incluyen:
- Un hospital puede crear equipos distintos para que enfermeras, médicos y cirujanas difunden comunicaciones. Esto es especialmente importante si el hospital depende de empleados temporales.
- Una universidad puede crear un equipo para todos los profesores de una universidad en particular, incluidos los profesores adjuntos que cambian con frecuencia.
- Una línea aérea quiere crear un equipo para cada vuelo (como un martes por la tarde sin escalas de Chicago a Atlanta) y que se asigne o quite automáticamente a una cuadrilla de pilotos que cambia con frecuencia según sea necesario.

Con esta característica, los miembros de un equipo determinado se actualizan automáticamente en función de un conjunto específico de criterios, en lugar de administrar manualmente la pertenencia. Para ello, un administrador de inquilinos puede asignar licencias de Azure AD Premium P1 y la pertenencia al equipo [a](/azure/active-directory/users-groups-roles/groups-dynamic-membership) las propiedades de Azure AD de cualquier usuario siempre que tenga un inquilino y una cuenta de administrador.

Microsoft Teams puede tardar entre unos minutos y hasta 2 horas en reflejar los cambios dinámicos de pertenencia una vez que entren en vigor en el grupo de Microsoft 365 para un equipo.

> [!NOTE]
> - Las reglas pueden definir quién es un miembro del equipo, pero no quién es el propietario del equipo.
> - Consulte [Límites y especificaciones de Microsoft Teams para](limits-specifications-teams.md) ver los límites actuales de los tamaños de equipo y canal.
> - Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas dinámicas de grupo.
> -    Los miembros no podrán dejar los equipos con el respaldo de grupos dinámicos.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>Crear y administrar un grupo de Microsoft 365 con pertenencia dinámica

Al iniciar sesión como administrador de inquilinos, siga las instrucciones de [Crear un grupo dinámico y compruebe el estado.](/azure/active-directory/users-groups-roles/groups-create-rule) Según sea necesario, consulte [Reglas de pertenencia dinámica para grupos en Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Crear un nuevo equipo con el grupo de Microsoft 365

Ahora, dé tiempo para que los cambios de pertenencia sumen efecto y cree un nuevo equipo como se describe en Crear un equipo a partir [de un grupo existente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>Aplicar pertenencia dinámica a un equipo existente

También puede tomar un equipo existente y cambiarlo para que tenga una pertenencia dinámica, como se describe en Cambiar la pertenencia a grupos estáticos a dinámica [en Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>Cambios en el comportamiento del cliente

Una vez que la pertenencia dinámica está habilitada para un equipo, los clientes de Teams ya no permitirán la administración de miembros para el equipo. Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de unirse y dejar el equipo están ocultas.