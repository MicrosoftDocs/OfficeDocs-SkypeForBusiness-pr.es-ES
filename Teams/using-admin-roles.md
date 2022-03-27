---
title: Usar roles de administrador de Microsoft Teams para administrar Teams
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
ms.openlocfilehash: c227abe677d75d06fd6577ccbfc8057c82f00002
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456963"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar roles de administrador de Microsoft Teams para administrar Teams

Con Azure Active Directory (Azure AD), puede designar administradores que necesitan diferentes niveles de acceso para administrar Microsoft Teams. Los administradores pueden administrar toda la carga Teams de trabajo o pueden tener permisos delegados para solucionar problemas de calidad de llamadas o administrar las necesidades de telefonía de su organización.

## <a name="teams-roles-and-capabilities"></a>Teams funciones y capacidades

Hay varios roles de administrador Teams disponibles: administrador de Teams, administrador de comunicaciones de Teams, especialista en soporte de comunicaciones de Teams, Teams técnico de soporte de comunicaciones y Teams administrador de dispositivos. Revise la tabla siguiente para comprender qué puede hacer cada rol y qué herramientas puede usar el administrador en el centro Microsoft Teams administración y PowerShell.

> [!NOTE]
> Skype Empresarial los administradores en línea pueden administrar **Teams** y **Skype Empresarial de** aplicaciones en línea a través de PowerShell.

Para seguir adelante, debe ser administrador. Las instrucciones para obtener los permisos se encuentran en este artículo.

<!-- add Global admin role? -->

| Rol                                    | Puede realizar estas tareas                                                           | Puede acceder a las siguientes herramientas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador de Teams             | Administre el Teams y administre y cree Microsoft 365 grupos.        | Todo en el centro Microsoft Teams administración y los controles de PowerShell asociados, incluidos:<ul><li> Administre reuniones, incluidas directivas de reunión, configuraciones y puentes de conferencia. <sup>1,2</sup></li><li>Administre la voz, incluidas las directivas de llamadas y el inventario y la asignación de números de teléfono. <sup>1,3</sup></li><li>Administre la mensajería, incluidas las directivas de mensajería. <sup>1,2</sup></li><li>Administre toda la configuración de toda la organización, incluida la federación, la actualización de equipos y la configuración del cliente de los equipos. <sup>1,2</sup></li><li>Administre los equipos de la organización y su configuración asociada, incluida la pertenencia (administración de grupos admitida a través de PowerShell, administración de equipos en el Teams de administración).<sup> 1,2</sup></li><li>Administre Teams dispositivos certificados y configure y asigne directivas de configuración.<sup> 1</sup></li><li>Vea la página de perfil de usuario y solucione problemas de calidad de llamadas de usuario con el conjunto de herramientas de solución de problemas avanzado. <sup>2</sup> </li><li>Acceder a todos los informes en el Microsoft Teams de administración</li><li> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con datos expuestos en el Panel de calidad de llamadas (CQD) a los usuarios afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite informes de calidad de llamadas según sea necesario. Upload y actualice los datos de creación de CQD.</li><li> [Publicar aplicaciones en el catálogo de aplicaciones de inquilino en el Microsoft Teams de administración](manage-apps.md)</li></ul> |
| Administrador de comunicaciones de Teams      | Administre las características de llamadas y reuniones dentro del Teams servicio.               | Administre reuniones, incluidas directivas de reunión, configuraciones y puentes de conferencia. <sup>1,2</sup><br><br> Administre la voz, incluidas las directivas de llamadas y el inventario y la asignación de números de teléfono. <sup>1,3</sup><br><br> Vea la página de perfil de usuario y solucione problemas de calidad de llamadas de usuario con el conjunto de herramientas de solución de problemas avanzado. <sup>2</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con datos expuestos en el Panel de calidad de llamadas (CQD) a los usuarios que se han visto afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite informes de calidad de llamadas según sea necesario. Upload y actualice los datos de creación de CQD.|
| Ingeniero de soporte en comunicaciones de Teams   | Solucione problemas de comunicaciones Teams mediante herramientas **avanzadas**. | Vea la página de perfil de usuario y solucione problemas de calidad de llamadas de usuario con el conjunto de herramientas de solución de problemas avanzado. <sup>2</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con datos expuestos en el Panel de calidad de llamadas (CQD) a los usuarios que se han visto afectados por la mala calidad de las llamadas. |
| Teams de soporte técnico de comunicaciones | Solucione problemas de comunicaciones Teams mediante **herramientas básicas**.    | Página de perfil de usuario de Access para solucionar problemas de llamadas en Análisis de llamadas. Solo puede ver la información de usuario del usuario específico que se busca. <sup>2</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de llamadas del inquilino con los datos expuestos en el Panel de calidad de llamadas (CQD). |
| Teams administrador de dispositivos              | Administre dispositivos configurados para su uso con Teams servicio.                    | Administre la configuración y actualizaciones del dispositivo, revise el estado y el estado del dispositivo de los periféricos conectados, configure y aplique perfiles de configuración y reinicie los dispositivos.<p>El Teams de administrador de dispositivos no proporciona acceso a datos de calidad de llamadas o análisis de llamadas. Para ver los datos de calidad de las llamadas o el análisis de llamadas, debe tener asignado el rol Teams administrador de comunicaciones. |

<sup>1</sup> [PowerShell: Microsoft Teams módulo](https://www.powershellgallery.com/packages/MicrosoftTeams/) (la versión pública 1.1.6 o posterior está integrada con Skype Empresarial Online Connector).<br>
<sup>2</sup> [Microsoft Teams de administración3](./manage-teams-skypeforbusiness-admin-center.md)
 Teams cuenta de administrador debe tener una licencia Teams usuario.<sup></sup>
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obtener más información sobre las herramientas de administración disponibles para administrar Microsoft Teams, vea [Administrar Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Para obtener más información sobre los límites, especificaciones y otros requisitos que se aplican a Teams, vea [Límites y especificaciones para Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Asignar usuarios a cada rol

Puede asignar usuarios a estos roles en Azure AD. Para obtener información sobre cómo asignar roles administrativos a un usuario en Azure AD, vea Asignar [un usuario a roles de administrador en Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles para cada rol

La mayoría de las herramientas de PowerShell para estos roles de administrador se encuentran en el módulo de PowerShell de Teams y es importante tener en cuenta que algunos de los cmdlets a los que estos roles de administrador tienen acceso para controlar la configuración compartida que también se usa para Skype Empresarial Online. 

Para ver la lista completa de cmdlets:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>Artículos relacionados

- [Microsoft Teams información general de PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](./assign-roles-permissions.md)
