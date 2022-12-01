---
title: Información general sobre la pertenencia dinámica para los equipos
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo Microsoft Teams admite equipos asociados con grupos de Microsoft 365 mediante la pertenencia dinámica.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65c747fea2b33f2fd18b004e9a16a2302702ec59
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198732"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>Información general sobre la pertenencia dinámica para los equipos

Microsoft Teams admite equipos asociados con Microsoft 365 grupos mediante *la pertenencia dinámica*. La pertenencia dinámica permite definir la pertenencia de un equipo mediante una o varias reglas que comprueban determinados atributos de usuario en Azure Active Directory (Azure AD). Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que cambian los atributos de usuario o los usuarios se unen y abandonan el inquilino.

Con la pertenencia dinámica puede configurar equipos para determinados grupos de usuarios de su organización. Entre los posibles escenarios se incluyen:
- Un hospital puede crear distintos equipos para que enfermeras, médicos y cirujanos difundan comunicaciones. Esto es especialmente importante si el hospital depende de los empleados temporales.
- Una universidad puede crear un equipo para todos los profesores de una universidad en particular, incluido un profesor adjunto que cambia con frecuencia.
- Una línea aérea desea crear un equipo para cada vuelo (como un martes por la tarde sin parar de Chicago a Atlanta) y tener una tripulación de vuelo que cambia con frecuencia automáticamente asignada o retirada según sea necesario.

Con esta característica, los miembros de un equipo determinado se actualizan automáticamente en función de un conjunto específico de criterios, en lugar de administrar manualmente la pertenencia. Para ello, es necesario que un [administrador de inquilinos asigne](/azure/active-directory/users-groups-roles/groups-dynamic-membership) licencias de Azure AD Premium P1 y la pertenencia a equipos a las propiedades de Azure AD de cualquier usuario, siempre que tenga un inquilino y una cuenta de administrador.

Microsoft Teams puede tardar entre unos minutos y un máximo de 2 horas en reflejar los cambios dinámicos de pertenencia una vez que entren en vigor en el grupo de Microsoft 365 para un equipo.

Al usar equipos con grupos dinámicos:

- Las reglas pueden definir quién es un miembro del equipo, pero no quién es el propietario del equipo.
- Los propietarios no podrán agregar ni quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas de grupo dinámicas.
- Los clientes de Teams no permiten la administración de miembros para el equipo. Las opciones para agregar miembros, editar roles de miembros, enviar y aprobar solicitudes de unión y dejar el equipo están ocultas.

Para crear un equipo que use la pertenencia dinámica, empiece [por crear un grupo de Microsoft 365 dinámico](/azure/active-directory/users-groups-roles/groups-create-rule) y, a continuación, [cree un equipo a partir de ese grupo](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).

Puede cambiar un equipo existente para que tenga una pertenencia dinámica. Vea [Cambiar la pertenencia a grupos estáticos a dinámica en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) para obtener información.

## <a name="related-topics"></a>Temas relacionados

[Límites y especificaciones para Microsoft Teams](limits-specifications-teams.md)

[Reglas de pertenencia dinámicas para grupos en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
