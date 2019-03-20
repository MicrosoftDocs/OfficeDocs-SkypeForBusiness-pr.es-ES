---
title: Usar los roles de administrador de Microsoft Teams para administrar Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
ms.reviewer: islubin
description: Aprenda a usar las funciones administrativas diferentes para administrar los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5280691b5272765b0c351c38a03e9711b9e0f1b0
ms.sourcegitcommit: 28dd9b8ca3de35a73e4d6923eff5546925435b8b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "30684052"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Usar los roles de administrador de Microsoft Teams para administrar Teams

Con Azure Active Directory (AD Azure), puede designar a los administradores que necesitan distintos niveles de acceso para la administración de Microsoft Teams. Los administradores pueden administrar la carga de trabajo completa de los equipos, o puede haber delegar permisos, para solucionar problemas de llamar a problemas de calidad o administración de telefonía de su organización necesita. 

## <a name="teams-roles-and-capabilities"></a>Roles de los equipos y funciones

Hay cuatro roles de administrador de equipos disponibles: Administrador de servicio de los equipos, el Administrador de comunicaciones de los equipos, especialista en soporte técnico de comunicaciones de los equipos y comunicaciones de los equipos ingeniero de soporte técnico. Revise la tabla siguiente para comprender lo que puede hacer cada rol y la administración de las herramientas que pueden usar en el centro de administración de Microsoft Teams y PowerShell.

<!-- add Global admin role? -->

| Rol | Puede realizar estas tareas | Puede obtener acceso a las siguientes herramientas |
|----- | ------------------ | ------------------------------ |
| Administrador de servicios de Teams | Administrar el servicio de Microsoft Teams y administrar y crear grupos de Office 365 | Todo el contenido en el centro de administración de Microsoft Teams y controles asociados de PowerShell, incluidos:<br><br> Administrar reuniones, incluida la conferencia, las configuraciones y directivas de puentes<sup>1,3</sup> de la reunión<br><br> Administrar voz, incluida la llamada a las directivas y número de inventario y asignación<sup>1</sup> de teléfono<br><br> Administración de mensajería, incluidas la mensajería de directivas<sup>1,3</sup><br><br> Administrar toda la configuración de toda la organización, incluida la federación, actualización de los equipos y los equipos cliente configuración<sup>1,3</sup><br><br> Administrar los equipos de la organización y sus valores asociados, incluyendo pertenencia (administración de grupo que se admiten mediante PowerShell, la administración de equipo en el portal de administración implantar) <sup>23</sup><br><br> Ver la página de perfil de usuario y solucionar los problemas de calidad de llamada de usuario utilizando de conjunto de herramientas de solución de problemas avanzada<sup>3</sup> <br><br> Obtener acceso, supervisar y solucionar problemas de llamada del inquilino calidad y confiabilidad mediante datos exponen en el panel de calidad de llamadas (CQD). Crear nuevos informes, actualizar y eliminar informes según sea necesario. Cargar y actualizar CQD creación de datos |
| Administrador de comunicaciones de Teams | Administre las características de reuniones y llamadas dentro del servicio de Microsoft Teams | Administrar reuniones, incluida la conferencia, las configuraciones y directivas de puentes<sup>1,3</sup> de la reunión<br><br> Administrar voz, incluida la llamada a las directivas y número de inventario y asignación<sup>1</sup> de teléfono<br><br> Ver la página de perfil de usuario y solucionar los problemas de calidad de llamada de usuario utilizando de conjunto de herramientas de solución de problemas avanzada<sup>3</sup> |
| Ingeniero de soporte en comunicaciones de Teams | Solucionar problemas de las comunicaciones dentro de los equipos mediante el uso de herramientas **Avanzadas** . | Ver la página de perfil de usuario y solucionar los problemas de calidad de llamada de usuario utilizando de conjunto de herramientas de solución de problemas avanzada<sup>3</sup> |
| Especialista en soporte técnico de comunicaciones de los equipos | Solucionar problemas de las comunicaciones dentro de los equipos mediante el uso de herramientas **básicas** .| Acceso a la página de perfil de usuario para solucionar problemas de las llamadas en llamar análisis. Solo se puede ver la información de usuario del usuario concreto que se está buscando.<sup>3</sup>

<sup>1</sup> [PowerShell - Skype para módulo empresarial](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - módulo de equipos de Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Centro de administración de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Para obtener más información acerca de las herramientas de administración disponibles para administrar Microsoft Teams, vea [Administración de equipos de Microsoft](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Para obtener más información acerca de los límites, especificaciones y otros requisitos que se aplican a los equipos, vea [los límites y las especificaciones de los equipos de Microsoft](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Asignar a usuarios a cada función

Puede asignar a usuarios a estos roles en Azure Active Directory. Para obtener información sobre cómo asignar funciones administrativas a un usuario en Active Directory de Azure, vea [asignar a un usuario a los roles de administrador de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles para cada función

La mayoría de las herramientas de PowerShell para estos roles de administrador live en el Skype para el módulo de PowerShell de negocio, y es importante tener en cuenta que algunos de los cmdlets que estos roles de administrador tienen acceso al control comparten de configuración que también se aprovecha de Skype para profesionales en línea. Para ver la lista completa de los cmdlets disponibles actualmente para un rol determinado en el Skype para el módulo de PowerShell de negocio de, siga estos pasos:

1. Asignar dicha función a un usuario (y asegúrese de que el usuario no tiene otras funciones).
2. Conectarse a la Skype para el módulo de PowerShell de negocio:<br>
   a. $session = nuevo csonlinesession<br>
   b. Import-pssession $session<br>
   c. Use **Get-módulo** para identificar el nombre de la sesión importado (será un nombre generado de forma aleatoria).<br>
3. Uso **Get-Command - módulo** <>*nombre desde arriba*para identificar todos los cmdlets disponibles

### <a name="related-topics"></a>Temas relacionados

- [Información general de PowerShell de equipos de Microsoft](teams-powershell-overview.md)
- [Los equipos de Microsoft PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

