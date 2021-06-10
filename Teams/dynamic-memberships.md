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
description: Obtenga información sobre cómo Microsoft Teams equipos asociados con Microsoft 365 mediante la pertenencia dinámica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856329"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Información general sobre la pertenencia dinámica para los equipos

Microsoft Teams admite equipos asociados con Microsoft 365 mediante la *pertenencia dinámica.* La pertenencia dinámica permite definir la pertenencia a un equipo mediante una o varias reglas que comprueban si hay determinados atributos de usuario en Azure Active Directory (Azure AD). Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que cambian los atributos de usuario o los usuarios se unen y abandonan el espacio empresarial.

Con la pertenencia dinámica, puede configurar equipos para determinadas cohortes de usuarios de su organización. Entre los posibles escenarios se incluyen:
- Un hospital puede crear equipos distintos para que enfermeras, médicos y cirujanas difunden comunicaciones. Esto es especialmente importante si el hospital depende de empleados temporales.
- Una universidad puede crear un equipo para todos los profesores de una universidad en particular, incluidos los profesores adjuntos que cambian con frecuencia.
- Una línea aérea quiere crear un equipo para cada vuelo (como un martes por la tarde sin escalas de Chicago a Atlanta) y que se asigne o quite automáticamente a una cuadrilla de pilotos que cambia con frecuencia según sea necesario.

Con esta característica, los miembros de un equipo determinado se actualizan automáticamente en función de un conjunto específico de criterios, en lugar de administrar manualmente la pertenencia. Para ello, un administrador de inquilinos puede asignar licencias de Azure AD Premium P1 y pertenencia al equipo [a](/azure/active-directory/users-groups-roles/groups-dynamic-membership) las propiedades de Azure AD de cualquier usuario siempre que tenga un inquilino y una cuenta de administrador.

Microsoft Teams puede tardar entre unos minutos y hasta 2 horas en reflejar los cambios dinámicos de pertenencia una vez que entren en vigor en el grupo de Microsoft 365 para un equipo.

Al usar equipos con grupos dinámicos:

- Las reglas pueden definir quién es un miembro del equipo, pero no quién es el propietario del equipo.
- Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas dinámicas de grupo.
- Teams clientes no permiten la administración de miembros para el equipo. Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de unirse y dejar el equipo están ocultas.

Para crear un equipo que use pertenencia dinámica, empiece por crear un grupo de Microsoft 365 dinámico y, [a](/azure/active-directory/users-groups-roles/groups-create-rule) continuación, cree un equipo [a partir de ese grupo.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

Puede cambiar un equipo existente para que tenga una pertenencia dinámica. Vea [Cambiar la pertenencia a grupos estáticos a dinámica en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) para obtener información.

## <a name="related-topics"></a>Temas relacionados

[Límites y especificaciones para Microsoft Teams](limits-specifications-teams.md)

[Reglas de pertenencia dinámica para grupos de Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
