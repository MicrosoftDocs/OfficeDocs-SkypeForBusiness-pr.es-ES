---
title: Usar roles de administrador de Microsoft Teams para administrar Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 17a8f6e9475355a5ee0f8960294bf3589d228ed1
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615456"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Usar roles de administrador de Microsoft Teams para administrar Teams

Con Azure Active Directory (Azure AD), puede designar administradores que necesiten diferentes niveles de acceso para administrar Microsoft Teams. Los administradores pueden administrar toda la carga de trabajo de Teams o pueden tener permisos delegados para solucionar problemas de calidad de las llamadas o administrar las necesidades de telefonía de su organización.

## <a name="teams-roles-and-capabilities"></a>Funciones y funcionalidades de Teams

Hay varios roles de administrador de Teams disponibles: administrador de Teams, administrador de comunicaciones de Teams, especialista en soporte técnico de comunicaciones de Teams, ingeniero de soporte técnico de comunicaciones de Teams y administrador de dispositivos de Teams. Revise la tabla siguiente para comprender qué puede hacer cada rol y qué herramientas puede usar el administrador en el Centro de administración de Microsoft Teams y PowerShell.

> [!NOTE]
> Los administradores de Skype Empresarial Online pueden administrar tanto las directivas de las aplicaciones de **Teams** y **Skype Empresarial Online** a través de PowerShell.

Para seguir los pasos, debe ser administrador. Las instrucciones para obtener los permisos se encuentran en este artículo.

<!-- add Global admin role? -->

| Rol                                    | Puede realizar estas tareas                                                           | Puede acceder a las siguientes herramientas                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrador de Teams             | Administre el servicio de Teams y administre y cree Grupos de Microsoft 365.        | Todo el contenido del Centro de administración de Microsoft Teams y los controles asociados de PowerShell, incluidos:<ul><li> Administre reuniones, incluidas las directivas de reunión, las configuraciones y los puentes de conferencia. <sup>1,2</sup></li><li>Administre la voz, incluidas las directivas de llamadas y el inventario y la asignación de números de teléfono. <sup>1,3</sup></li><li>Administre los mensajes, incluidas las directivas de mensajería. <sup>1,2</sup></li><li>Administre toda la configuración de toda la organización, incluida la federación, la actualización de equipos y la configuración de cliente de equipos. <sup>1,2</sup></li><li>Administre los equipos de la organización y su configuración asociada, incluida la pertenencia a grupos (administración de grupos admitida a través de PowerShell, administración de equipos en el Centro de administración de Teams). <sup>1,2</sup></li><li>Administre dispositivos certificados por Teams y configure y asigne directivas de configuración. <sup>1</sup></li><li>Ver la página de perfil de usuario y solucionar problemas de calidad de llamadas de usuario con el conjunto de herramientas avanzadas de solución de problemas. <sup>2</sup> </li><li>Obtener acceso a todos los informes en el Centro de administración de Microsoft Teams</li><li> Acceda, supervise y solucione los problemas de confiabilidad y calidad de las llamadas del inquilino usando los datos expuestos en el Panel de calidad de llamadas (CQD) hacia abajo para los usuarios afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite los informes de calidad de llamada según sea necesario. Cargue y actualice datos de compilación del CQD.</li><li> [Publicar aplicaciones en el catálogo de aplicaciones de inquilino en el Centro de administración de Microsoft Teams](manage-apps.md)</li></ul> |
| Administrador de comunicaciones de Teams      | Administre las características de llamadas y reuniones en el servicio de Teams.               | Administre reuniones, incluidas las directivas de reunión, las configuraciones y los puentes de conferencia. <sup>1,2</sup><br><br> Administre la voz, incluidas las directivas de llamadas y el inventario y la asignación de números de teléfono. <sup>1,3</sup><br><br> Ver la página de perfil de usuario y solucionar problemas de calidad de llamadas de usuario con el conjunto de herramientas avanzadas de solución de problemas. <sup>2</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de las llamadas del inquilino usando los datos expuestos en el Panel de calidad de llamadas (CQD) hacia abajo para los usuarios que se ven afectados por la mala calidad de las llamadas. Cree nuevos informes de calidad de llamadas, actualice y quite los informes de calidad de llamada según sea necesario. Cargue y actualice datos de compilación del CQD.|
| Ingeniero de soporte en comunicaciones de Teams   | Solucione problemas de comunicación en Teams con herramientas **avanzadas** . | Ver la página de perfil de usuario y solucionar problemas de calidad de llamadas de usuario con el conjunto de herramientas avanzadas de solución de problemas. <sup>2</sup> <br><br> Acceda, supervise y solucione problemas de confiabilidad y calidad de las llamadas del inquilino usando los datos expuestos en el Panel de calidad de llamadas (CQD) hacia abajo para los usuarios que se ven afectados por la mala calidad de las llamadas. |
| Especialista en soporte técnico de comunicaciones de Teams | Solucione problemas de comunicaciones en Teams con herramientas **básicas** .    | Acceda a la página de perfil de usuario para solucionar problemas de llamadas en Análisis de llamadas. Solo puede ver la información del usuario específico que se está buscando. <sup>2</sup> <br><br> Acceda, supervise y solucione problemas de calidad y confiabilidad de las llamadas del inquilino usando los datos expuestos en el Panel de calidad de llamadas (CQD). |
| Administrador de dispositivos de Teams              | Administrar dispositivos configurados para su uso con el servicio de Teams.                    | Administra las actualizaciones y la configuración del dispositivo, revisa el estado y el estado de los periféricos conectados, configura y aplica perfiles de configuración y reinicia dispositivos.<p>El rol Administrador de dispositivos de Teams no proporciona acceso a datos de calidad de llamadas ni análisis de llamadas. Para ver datos de calidad de llamadas o análisis de llamadas, debe tener asignado el rol administrador de comunicaciones de Teams. |

<sup>1</sup> [PowerShell: módulo de Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) (la versión pública 1.1.6 o posterior se integra con Skype Empresarial Conector en línea).<br>
<sup>2</sup> [Centro](./manage-teams-skypeforbusiness-admin-center.md)
 de administración de Microsoft Teams<sup>3</sup> La cuenta de administrador de Teams debe tener una licencia válida de Teams.
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Para obtener más información sobre las herramientas de administración disponibles para administrar Microsoft Teams, consulte [Administración de Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Para obtener más información sobre los límites, las especificaciones y otros requisitos que se aplican a Teams, consulte [Límites y especificaciones para Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Asignar usuarios a cada rol

Puede asignar usuarios a estos roles en Azure AD. Para obtener información sobre cómo asignar roles administrativos a un usuario en Azure AD, vea [Asignar un usuario a roles de administrador en Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles para cada rol

La mayoría de las herramientas de PowerShell para estos roles de administrador se encuentran en el módulo PowerShell de Teams y es importante tener en cuenta que algunos de los cmdlets en los que estos roles de administrador tienen acceso para controlar la configuración compartida que también se usa para Skype Empresarial Online. 

Para ver la lista completa de cmdlets:

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>Artículos relacionados

- [Introducción a Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Asignar miembros y propietarios de equipo en Microsoft Teams](./assign-roles-permissions.md)
