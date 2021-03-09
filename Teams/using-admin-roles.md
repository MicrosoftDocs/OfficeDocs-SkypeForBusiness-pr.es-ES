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
description: Obtenga información sobre cómo usar los roles administrativos para designar administradores que necesitan diferentes niveles de acceso para administrar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: feccaa2662189016c721a2bf11629598d90f0501
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558399"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar los roles de administrador de Microsoft Teams para administrar Teams

Con Azure Active Directory (Azure AD), puede designar administradores que necesiten diferentes niveles de acceso para administrar Microsoft Teams. Los administradores pueden administrar toda la carga de trabajo de Teams o pueden tener permisos delegados para solucionar problemas de calidad de llamadas o administrar las necesidades de telefonía de su organización.

## <a name="teams-roles-and-capabilities"></a>Roles y capacidades de Teams

Hay varios roles de administrador de Teams disponibles: administrador de servicio de Teams, administrador de comunicaciones de Teams, especialista en soporte de comunicaciones de Teams, ingeniero de soporte de comunicaciones de Teams y administrador de dispositivos de Teams. Revise la tabla siguiente para comprender qué puede hacer cada rol y qué herramientas puede usar el administrador en el Centro de administración de Microsoft Teams y PowerShell.

Para seguir adelante, debe ser administrador. Las instrucciones para obtener los permisos se encuentran en este artículo.

<!-- add Global admin role? -->

| Rol                                    | Puede realizar estas tareas                                                           | Puede acceder a las siguientes herramientas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador de servicios de Teams             | Administre el servicio de Teams y administre y cree grupos de Microsoft 365.        | Todo en el centro de administración de Microsoft Teams y los controles de PowerShell asociados, incluidos:<ul><li> Administre reuniones, incluidas directivas de reunión, configuraciones y puentes de conferencia. <sup>1,3</sup></li><li>Administre la voz, incluidas las directivas de llamadas y el inventario y la asignación de números de teléfono. <sup>1</sup></li><li>Administre la mensajería, incluidas las directivas de mensajería. <sup>1,3</sup></li><li>Administre toda la configuración de toda la organización, incluida la federación, la actualización de equipos y la configuración del cliente de los equipos. <sup>1,3</sup></li><li>Administre los equipos de la organización y su configuración asociada, incluida la pertenencia (administración de grupos admitida a través de PowerShell, administración de equipos en el Centro de administración de Teams). <sup>2,3</sup></li><li>Administre dispositivos certificados por Teams y configure y asigne directivas de configuración. <sup>2</sup></li><li>Vea la página de perfil de usuario y solucione problemas de calidad de llamadas de usuario con el conjunto de herramientas de solución de problemas avanzado. <sup>3</sup> </li><li>Acceder a todos los informes en el Centro de administración de Microsoft Teams</li><li> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con datos expuestos en el Panel de calidad de llamadas (CQD) a los usuarios afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite informes de calidad de llamadas según sea necesario. Cargar y actualizar datos de creación de CQD.</li><li> [Publicar aplicaciones en el catálogo de aplicaciones de inquilino en el Centro de administración de Microsoft Teams](manage-apps.md)</li></ul> |
| Administrador de comunicaciones de Teams      | Administre las características de llamadas y reuniones en el servicio de Teams.               | Administre reuniones, incluidas directivas de reunión, configuraciones y puentes de conferencia. <sup>1,3</sup><br><br> Administre la voz, incluidas las directivas de llamadas y el inventario y la asignación de números de teléfono. <sup>1</sup><br><br> Vea la página de perfil de usuario y solucione problemas de calidad de llamadas de usuario con el conjunto de herramientas de solución de problemas avanzado. <sup>3</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con datos expuestos en el Panel de calidad de llamadas (CQD) a los usuarios que se han visto afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite informes de calidad de llamadas según sea necesario. Cargar y actualizar datos de creación de CQD.|
| Ingeniero de soporte en comunicaciones de Teams   | Solucione problemas de comunicaciones en Teams con **herramientas avanzadas.** | Vea la página de perfil de usuario y solucione problemas de calidad de llamadas de usuario con el conjunto de herramientas de solución de problemas avanzado. <sup>3</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con datos expuestos en el Panel de calidad de llamadas (CQD) a los usuarios que se han visto afectados por la mala calidad de las llamadas. |
| Especialista en soporte técnico de Comunicaciones de Teams | Solucione problemas de comunicaciones en Teams con **herramientas** básicas.    | Página de perfil de usuario de Access para solucionar problemas de llamadas en Análisis de llamadas. Solo se puede ver la información de usuario del usuario concreto que se está buscando.<sup>3</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con los datos expuestos en el Panel de calidad de llamadas (CQD). |
| Administrador de dispositivos de Teams              | Administrar dispositivos configurados para su uso con el servicio de Teams.                    | Administre la configuración y actualizaciones del dispositivo, revise el estado y el estado del dispositivo de los periféricos conectados, configure y aplique perfiles de configuración y reinicie los dispositivos.<p>El rol de administrador de dispositivos de Teams no proporciona acceso a datos de calidad de llamadas o análisis de llamadas. Para ver datos de calidad de llamadas o análisis de llamadas, debe tener asignado el rol de administrador de comunicaciones de Teams. |

<sup>1</sup> [PowerShell : módulo de Skype Empresarial](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell : módulo Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 Centro</sup> [de administración de Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obtener más información sobre las herramientas de administración disponibles para administrar Microsoft Teams, vea [Administrar Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)

Para obtener más información sobre los límites, especificaciones y otros requisitos que se aplican a Teams, vea [Límites y especificaciones de Microsoft Teams.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>Asignar usuarios a cada rol

Puede asignar usuarios a estos roles en Azure AD. Para obtener información sobre cómo asignar roles administrativos a un usuario en Azure AD, vea Asignar un usuario [a roles de administrador en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles para cada rol

La mayoría de las herramientas de PowerShell para estos roles de administrador se encuentran en el módulo de PowerShell de Teams y es importante tener en cuenta que algunos de los cmdlets que estos roles de administrador tienen acceso para controlar la configuración compartida que también se usa para Skype Empresarial Online. 

Para ver la lista completa de cmdlets:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-topics"></a>Temas relacionados

- [Información general sobre PowerShell de Microsoft Teams](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)
