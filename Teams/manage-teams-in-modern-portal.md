---
title: Administrar los equipos en el centro de administración de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: Obtenga información sobre cómo ver o actualizar los equipos en el centro de administración de Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202752"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Administrar los equipos en el centro de administración de Microsoft Teams
==========================================


## <a name="overview"></a>Información general

Como un administrador de TI, es posible que necesite vista o actualización de los equipos de su organización ha configurado para la colaboración o necesite para llevar a cabo las acciones de corrección, como la asignación de propietarios de los equipos sin dueño. Puede administrar los equipos que se usan en la organización a través del módulo de PowerShell de los equipos de Microsoft y el centro de administración de Microsoft Teams. Para las capacidades de administración completa con estos dos conjuntos de herramientas, debe asegurarse de que se le asigna uno de los siguientes roles:

- Administrador global
- Administrador de servicios de Teams

Encontrará más información acerca de las funciones de administración en los equipos de [los roles de administrador de utilizar equipos de Microsoft para administrar los equipos](using-admin-roles.md)y puede leer más información acerca de cómo usar los cmdlets de PowerShell para la administración de equipos en la [referencia del cmdlet de equipos de Microsoft](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

En este artículo se proporciona una visión general de las herramientas de administración de equipos en el centro de administración de Microsoft Teams.

## <a name="teams-overview-grid"></a>Cuadrícula de visión general de los equipos

Herramientas de administración de los equipos se encuentran en el nodo de **los equipos** en el centro de administración de Microsoft Teams. (En el centro de administración, seleccione **los equipos** > **administrar equipos**.) Cada equipo se respaldadas por un grupo de Office 365, y este nodo proporciona una vista de grupos que se han habilitado para los equipos de la organización de Microsoft.

![Cuadrícula de visión general de los equipos](media/manage-teams-in-modern-portal-image1.png)  

La cuadrícula muestra las siguientes propiedades:

- **Nombre de equipo**
- **Canales** : un recuento de todos los canales en el equipo, incluido el canal General de forma predeterminada.
- **Los usuarios** : un recuento del total de usuarios, incluidos los propietarios, los invitados y miembros desde el inquilino.
- **Los propietarios de** -un recuento de los propietarios de este equipo.
- **Los invitados** - un recuento de los usuarios de invitado de Azure Active Directory B2B que son miembros de este equipo.
- **Privacidad** - la visibilidad/AccessType del grupo de realizar la copia de Office 365.
- **Estado** : el archivado o estado activo para este equipo.  Obtenga más información sobre el archivado de los equipos en el [archivo o la restauración de un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **GroupID** - GroupID único del grupo de realizar la copia de Office 365
- **Clasificación** - la clasificación (si se usan en la organización) que se asigna al grupo de realizar la copia de Office 365.  Obtenga más información acerca de las clasificaciones en [crear clasificaciones para los grupos de Office en su organización](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **Descripción** : la descripción para el grupo de realizar la copia de Office 365

### <a name="search"></a>Búsqueda

Búsqueda actualmente es compatible con la cadena "Comienza por" y busca en el campo **nombre del equipo** .

### <a name="edit"></a>Editar

Puede editar la configuración específica de equipo y grupo seleccionando un equipo de la cuadrícula y, a continuación, seleccionando el botón **Editar** .

![Editar equipo](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Perfiles de equipo

Puede navegar a la página de perfil de equipo de cualquier equipo de la cuadrícula de visión general de los equipos principal haciendo clic en el nombre de equipo. La página de perfil de equipo muestra los miembros, los propietarios y los invitados que pertenecen al equipo (y su copia de grupo de Office 365), así como canales y la configuración del grupo. Desde la página de perfil del equipo, se puede:

- Agregar o quitar miembros y propietarios.
- Agregar o quitar canales (tenga en cuenta que no se puede quitar el canal General).
- Actualización del equipo y configuración de grupo.
 
![Perfiles de equipo](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Realizar cambios en los equipos

Puede cambiar los siguientes elementos de un equipo:
- **Los usuarios en el equipo** , puede agregar o quitar miembros y promover o disminuir el nivel de los propietarios de
- **Canales** : puede agregar nuevos canales o quitar canales existentes.  No se puede eliminar el canal "General" de forma predeterminada y una vez creados sólo se puede editar el nombre del canal, no descripción.
- **Nombre de equipo**
- **Descripción de equipo**
- **Privacidad del equipo** - público o privado
- **Clasificación de equipo** - respaldados por sus clasificaciones de grupo de Office 365
- **Configuración del miembro de equipo** : configuración de miembro de equipo seleccione

## <a name="other-supported-changes-to-teams"></a>Otros cambios admitidos para los equipos

- **Eliminar** - eliminación de un equipo es una eliminación temporalmente del equipo y el grupo correspondiente de Office 365.  Para restaurar un equipo eliminado por error, siga las instrucciones que aparecen en la [restauración de un grupo de 365 eliminado de Office](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).
- **Archivo** - archivado un equipo pone el equipo en modo de sólo lectura dentro de Microsoft Teams.  Como administrador, puede archivar y unarchive los equipos en nombre de la organización a través del portal de administración.


Se registran los cambios que realice en un equipo. Si modifica la configuración de grupo (cambiar el nombre, descripción, foto, privacidad, clasificación o los miembros del equipo), estos cambios se expresarán a usted a través de la canalización de auditoría. Si va a realizar acciones contra la configuración específica de los equipos, los cambios se realiza un seguimiento y se expresarán en el canal general del equipo.

## <a name="troubleshooting"></a>Solución de problemas

**Problema: Los equipos que faltan en la cuadrícula de visión general del equipo**

Al escribir el centro de administración de Microsoft Teams, debajo de la opción de **los equipos** faltan algunas de sus equipos desde la lista en la cuadrícula de visión general de los equipos.

**Causa**: este problema se produce cuando el equipo de perfil se incorrectamente (o no todavía) generó el sistema que puede dar lugar a una propiedad que faltan para que se reconozca.

**Solución: Establezca manualmente la propiedad en el valor correcto a través de MS Graph**

Reemplace **{groupid}** en la consulta para el GroupId real en cuestión, que se puede obtener a través de la Exchange Online powershell, con el cmdlet **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como el atributo "**ExternalDirectoryObjectId**".

1. [El Explorador de gráfico](https://developer.microsoft.com/en-us/graph/graph-explorer) de acceso

2. Inicie sesión en el Explorador de gráfico en el menú de la izquierda

3. Cambie la línea de consulta para: revisión > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. Agregue el siguiente valor en el cuerpo de solicitud: {"resourceProvisioningOptions": ["equipo"]}

5. Ejecute la consulta en la esquina superior derecha.

6. Confirme que el equipo correctamente aparece en el centro de administración de Microsoft Teams - información general del equipo


## <a name="learn-more"></a>Más información

[Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Roles de administrador en Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

