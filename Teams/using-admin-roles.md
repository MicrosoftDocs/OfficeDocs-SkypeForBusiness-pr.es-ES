---
title: Usar los roles de administrador de Microsoft Teams para administrar equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
ms.reviewer: islubin
description: Aprenda a usar los distintos roles administrativos para administrar equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97288109f7998a8d29520169e229a5546da94bc5
ms.sourcegitcommit: e43a66a7f769f855dc45c1bb7f83636d0390949b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "37616062"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar los roles de administrador de Microsoft Teams para administrar equipos

Con Azure Active Directory (Azure AD) puede designar administradores que necesiten diferentes niveles de acceso para administrar Microsoft Teams. Los administradores pueden administrar toda la carga de trabajo de Teams o pueden tener permisos delegados para solucionar problemas de calidad de las llamadas o para administrar las necesidades de telefonía de su organización. 

## <a name="teams-roles-and-capabilities"></a>Funciones y capacidades de Teams

Hay cuatro roles de administrador disponibles: el administrador de servicios de Teams, el administrador de comunicaciones de equipos, el especialista de soporte técnico de comunicaciones y el ingeniero de soporte de comunicaciones de Teams. Revise la tabla siguiente para comprender qué puede hacer cada rol y qué herramientas puede usar el administrador en el centro de administración de Microsoft Teams y PowerShell.



<!-- add Global admin role? -->

| Rol | Puede realizar estas tareas | Puede acceder a las siguientes herramientas |
|----- | ------------------ | ------------------------------ |
| Administrador de servicios de Teams | Administrar el servicio de Teams y administrar y crear grupos de 365 de Office | Todo lo que hay en el centro de administración de Microsoft Teams y los controles de PowerShell asociados:<ul><li> Administrar reuniones, incluidas las directivas de reuniones, configuraciones y puentes de conferencia. <sup>1, 3</sup></li><li>Administra la voz, incluidas las directivas de llamadas y el inventario de números de teléfono y la asignación. <sup>1</sup></li><li>Administrar mensajería, incluidas las directivas de mensajería. <sup>1, 3</sup></li><li>Administrar toda la configuración de toda la organización, incluidos la Federación, la actualización de Teams y la configuración del cliente de Teams. s<sup>1, 3</sup></li><li>Administre los equipos de la organización y su configuración asociada, incluida la pertenencia (administración de grupos admitida a través de PowerShell, la administración de equipos en el centro de administración de Teams). <sup>23</sup></li><li>Ver la página de Perfil de usuario y solucionar problemas de calidad de llamadas de usuario mediante el conjunto de herramientas avanzado para solucionar problemas. <sup>3</sup> </li><li> Acceder, supervisar y solucionar problemas de la calidad de las llamadas y de la fiabilidad de los inquilinos con los datos expuestos en el panel de calidad de llamadas (CQD) a los usuarios afectados por la mala calidad de las llamadas. Crear nuevos informes, actualizar y eliminar informes según sea necesario. Cargue y actualice los datos de compilación del CQD.</li><li> [Publicar aplicaciones en el catálogo de aplicaciones de inquilino del cliente de Teams](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)</li></ul> |
| Administrador de comunicaciones de Teams | Administrar las características de llamadas y reuniones dentro del servicio de Teams. | Administrar reuniones, incluidas las directivas de reuniones, configuraciones y puentes de conferencia. <sup>1, 3</sup><br><br> Administra la voz, incluidas las directivas de llamadas y el inventario de números de teléfono y la asignación. <sup>1</sup><br><br> Ver la página de Perfil de usuario y solucionar problemas de calidad de llamadas de usuario con el conjunto de herramientas de solución de problemas avanzado. <sup>3</sup> <br><br> Acceda, monitoree y solucione problemas de calidad de llamadas y confiabilidad de los inquilinos con los datos expuestos en el panel de calidad de llamadas (CQD) para los usuarios que se vean afectados por la mala calidad de las llamadas. Crear nuevos informes, actualizar y eliminar informes según sea necesario. Cargue y actualice los datos de compilación del CQD.|
| Ingeniero de soporte en comunicaciones de Teams | Solucione problemas de comunicación dentro de Teams mediante herramientas **avanzadas** . | Ver la página de Perfil de usuario y solucionar problemas de calidad de llamadas de usuario mediante el conjunto de herramientas avanzado para solucionar problemas. <sup>3</sup> <br><br> Acceda, monitoree y solucione problemas de calidad de llamadas y confiabilidad de los inquilinos con los datos expuestos en el panel de calidad de llamadas (CQD) para los usuarios que se vean afectados por la mala calidad de las llamadas. |
| Especialista de soporte técnico de comunicaciones de Teams | Solucione problemas de comunicación dentro de Teams con las herramientas **básicas** .| Página de Perfil de usuario de Access para la solución de problemas de llamadas en análisis de llamadas. Solo se puede ver la información de usuario del usuario concreto que se está buscando.<sup>3</sup> <br><br> Acceder, supervisar y solucionar problemas de calidad de llamadas y confiabilidad de los inquilinos con los datos expuestos en el panel de calidad de llamadas (CQD).  

<sup>1</sup> [PowerShell: módulo de Skype empresarial](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell: Módulo Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [centro de administración de Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Para obtener más información sobre las herramientas de administración disponibles para administrar Microsoft Teams, consulte [Administración de Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Para obtener más información sobre los límites, las especificaciones y otros requisitos aplicables a los equipos, consulte [límites y especificaciones de Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Asignar usuarios a cada rol

Puede asignar usuarios a estos roles en Azure AD. Para obtener información sobre cómo asignar roles administrativos a un usuario en Azure AD, consulte [asignar un usuario a roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles para cada rol

La mayoría de las herramientas de PowerShell para estas funciones de administrador en vivo en el módulo de PowerShell de Skype empresarial y es importante tener en cuenta que algunos de los cmdlets de estos roles de administrador tienen acceso para controlar la configuración compartida que también se usa para Skype empresarial online. El rol de administrador de Skype empresarial también tiene acceso a todos los cmdlets en el módulo de PowerShell de Skype empresarial.

Para ver la lista completa de cmdlets disponibles actualmente para un rol determinado en el módulo de PowerShell de Skype empresarial, siga estos pasos:

1. Asigne ese rol a un usuario (y asegúrese de que el usuario no tiene ningún otro rol).
2. Conéctese al módulo de PowerShell de Skype empresarial:<br>
   a. $session = New-csonlinesession<br>
   b. $Session Import-pssession<br>
   c. Use **Get-Module** para identificar el nombre de la sesión importada (será un nombre generado aleatoriamente).<br>
3. Use el nombre **get-command-Module** <*de arriba*> para identificar todos los cmdlets disponibles

### <a name="related-topics"></a>Temas relacionados

- [Información general de Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

