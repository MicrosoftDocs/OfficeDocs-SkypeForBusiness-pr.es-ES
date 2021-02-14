---
title: Usar los roles de administrador de Microsoft Teams para administrar Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: Obtenga información sobre cómo usar los roles administrativos para designar administradores que necesitan distintos niveles de acceso para administrar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 637d6e63b0eabdc9517e8d5cd5986ae7661ad118
ms.sourcegitcommit: 032a22c8b61456dcbd798ec390f0ae1ca7d8eda0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357618"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar los roles de administrador de Microsoft Teams para administrar Teams

Con Azure Active Directory (Azure AD), puede designar administradores que necesiten distintos niveles de acceso para administrar Microsoft Teams. Los administradores pueden administrar toda la carga de trabajo de Teams o pueden tener permisos delegados para solucionar problemas de calidad de llamadas o administrar las necesidades de telefonía de su organización.

## <a name="teams-roles-and-capabilities"></a>Roles y capacidades de Teams

Hay varios roles de administrador de Teams disponibles: administrador de servicios de Teams, administrador de comunicaciones de Teams, especialista de soporte de comunicaciones de Teams, ingeniero de soporte técnico de comunicaciones de Teams y administrador de dispositivos de Teams. Revise la tabla siguiente para comprender qué puede hacer cada rol y qué herramientas puede usar el administrador en el Centro de administración de Microsoft Teams y PowerShell.

Para seguir los pasos, debe ser administrador. Las instrucciones para obtener los permisos están en este artículo.

<!-- add Global admin role? -->

| Rol                                    | Puede realizar estas tareas                                                           | Puede acceder a las siguientes herramientas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador de servicios de Teams             | Administre el servicio Teams y administre y cree Grupos de Microsoft 365.        | Todo el contenido del Centro de administración de Microsoft Teams y los controles de PowerShell asociados, incluidos:<ul><li> Administre reuniones, incluidas las directivas de reuniones, configuraciones y puentes de conferencia. <sup>1,3</sup></li><li>Administre la voz, incluidas las directivas de llamadas y el inventario de números de teléfono y las asignaciones. <sup>1</sup></li><li>Administrar la mensajería, incluidas las directivas de mensajería. <sup>1,3</sup></li><li>Administre toda la configuración de toda la organización, incluida la federación, la actualización de equipos y la configuración del cliente de equipos. <sup>1,3</sup></li><li>Administre los equipos de la organización y su configuración asociada, incluida la pertenencia (administración de grupos admitida a través de PowerShell, administración de equipos en el Centro de administración de Teams). <sup>2,3</sup></li><li>Administre dispositivos certificados para Teams y configure y asigne directivas de configuración. <sup>2</sup></li><li>Vea la página de perfil de usuario y solucione los problemas de calidad de las llamadas de los usuarios con los conjuntos de herramientas de solución de problemas avanzados. <sup>3</sup> </li><li>Acceder a todos los informes en el Centro de administración de Microsoft Teams</li><li> Acceda, supervise y solucione los problemas relacionados con la calidad y la confiabilidad de las llamadas del inquilino mediante los datos expuestos en el panel de calidad de llamadas (CQD) a los usuarios afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite los informes de calidad de llamadas según sea necesario. Cargue y actualice los datos de creación del CQD.</li><li> [Publicar aplicaciones en el catálogo de aplicaciones del inquilino en el Centro de administración de Microsoft Teams](manage-apps.md)</li></ul> |
| Administrador de comunicaciones de Teams      | Administre las características de llamadas y reuniones en el servicio teams.               | Administre reuniones, incluidas las directivas de reuniones, configuraciones y puentes de conferencia. <sup>1,3</sup><br><br> Administre la voz, incluidas las directivas de llamadas y el inventario de números de teléfono y las asignaciones. <sup>1</sup><br><br> Vea la página de perfil de usuario y solucione los problemas de calidad de las llamadas de los usuarios con el conjunto avanzado de herramientas de solución de problemas. <sup>3</sup> <br><br> Acceda, supervise y solucione los problemas relacionados con la calidad y la confiabilidad de las llamadas del inquilino mediante los datos expuestos en el panel de calidad de llamadas (CQD) a los usuarios afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite los informes de calidad de llamadas según sea necesario. Cargue y actualice los datos de creación del CQD.|
| Ingeniero de soporte en comunicaciones de Teams   | Solucione problemas de comunicaciones en Teams con **herramientas** avanzadas. | Vea la página de perfil de usuario y solucione los problemas de calidad de las llamadas de los usuarios con los conjuntos de herramientas de solución de problemas avanzados. <sup>3</sup> <br><br> Acceda, supervise y solucione los problemas relacionados con la calidad y la confiabilidad de las llamadas del inquilino mediante los datos expuestos en el panel de calidad de llamadas (CQD) a los usuarios afectados por la mala calidad de las llamadas. |
| Especialista de soporte técnico de comunicaciones de Teams | Solucione problemas de comunicaciones en Teams con **herramientas** básicas.    | Página de perfil de usuario de Access para solucionar problemas de llamadas en Análisis de llamadas. Solo se puede ver la información de usuario del usuario concreto que se está buscando.<sup>3</sup> <br><br> Acceda, supervise y solucione los problemas de calidad y fiabilidad de las llamadas del inquilino con los datos que se exponen en el panel de calidad de llamadas. |
| Administrador de dispositivos de Teams              | Administre los dispositivos configurados para su uso con el servicio Teams.                    | Administre la configuración y las actualizaciones del dispositivo, revise el estado y el estado del dispositivo de los periféricos conectados, configure y aplique perfiles de configuración y reinicie dispositivos.<p>El rol de administrador de dispositivos de Teams no proporciona acceso a datos de calidad de llamadas o análisis de llamadas. Para ver datos de calidad de llamadas o análisis de llamadas, debe tener asignado el rol de administrador de comunicaciones de Teams. |

<sup>1</sup> [PowerShell - Módulo de Skype Empresarial](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Módulo Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 Centro</sup> [de administración de Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obtener más información sobre las herramientas de administración disponibles para administrar Microsoft Teams, vea [Administrar Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)

Para obtener más información sobre los límites, las especificaciones y otros requisitos que se aplican a Teams, vea Límites y [especificaciones para Microsoft Teams.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>Asignar usuarios a cada rol

Puede asignar usuarios a estos roles en Azure AD. Para obtener información sobre cómo asignar roles administrativos a un usuario en Azure AD, vea Asignar un usuario a roles de [administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles para cada rol

La mayoría de las herramientas de PowerShell para estos roles de administrador se encuentran en el módulo PowerShell de Skype Empresarial y es importante tener en cuenta que algunos de los cmdlets que estos roles de administrador tienen acceso para controlar la configuración compartida que también se usa para Skype Empresarial Online. El rol de administrador de Skype Empresarial también tiene acceso a todos los cmdlets del módulo PowerShell de Skype Empresarial.

Para ver la lista completa de cmdlets disponibles actualmente para un rol determinado en el módulo de PowerShell de Skype Empresarial, siga estos pasos:

1. Asigne ese rol a un usuario (y asegúrese de que no tiene ningún otro rol).
2. Conectarse al módulo de PowerShell de Skype Empresarial:<br>
   a. $session = new-csonlinesession<br>
   b. Importar-pssession $session<br>
   c. Use **Get-Module** para identificar el nombre de la sesión importada (será un nombre generado de forma aleatoria).<br>
3. Use **Get-Command -Module**  < *name de arriba>* identificar todos los cmdlets disponibles

### <a name="related-topics"></a>Temas relacionados

- [Información general sobre PowerShell de Microsoft Teams](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

