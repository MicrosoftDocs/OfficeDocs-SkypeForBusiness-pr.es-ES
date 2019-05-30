---
title: Administrar equipos en el Centro de administración de Microsoft Teams
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
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548273"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Administrar equipos en el Centro de administración de Microsoft Teams
==========================================


## <a name="overview"></a>Información general

Como administrador de ti, es posible que necesite ver o actualizar los equipos que su organización ha configurado para la colaboración, o es posible que tenga que realizar acciones de corrección como asignar propietarios a equipos sin propietario. Puede administrar los equipos que se usan en la organización a través del módulo Microsoft Teams PowerShell y el centro de administración de Microsoft Teams. Para obtener capacidades de administración completas con estos dos conjuntos de herramientas, debe asegurarse de que tiene asignada una de las siguientes funciones:

- Administrador global
- Administrador de servicios de Teams

Puede obtener más información sobre los roles de administrador en Teams en [usar los roles de administrador de Microsoft Teams para administrar equipos](using-admin-roles.md)y puede obtener más información sobre cómo usar los cmdlets de PowerShell para administrar equipos en la [Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps).  

Este artículo proporciona una descripción general de las herramientas de administración de Teams en el centro de administración de Microsoft Teams.

## <a name="teams-overview-grid"></a>Cuadrícula de información general de Teams

Las herramientas de administración para Teams **** se encuentran en el nodo Teams del centro de administración de Microsoft Teams. (En el centro de administración, seleccione **Teams** > **Manage Teams**). Cada equipo está respaldado por un grupo de Office 365, y este nodo proporciona una vista de los grupos que se han habilitado en Microsoft Teams.

![Captura de pantalla de la cuadrícula de información general de Teams](media/manage-teams-in-modern-portal-image1.png)  

La cuadrícula muestra las siguientes propiedades:

- **Nombre del equipo**
- **Canales** : un recuento de todos los canales del equipo, incluido el canal general predeterminado.
- **Usuarios** : un recuento de total de usuarios, incluidos los propietarios, los invitados y los miembros de su inquilino.
- **Propietarios** : un recuento de propietarios de este equipo.
- **Invitados** : un recuento de usuarios invitados B2B de Azure Active Directory que son miembros de este equipo.
- **Privacidad** : la visibilidad/AccessType del grupo de respaldo de la oficina de 365.
- **Estado** : el estado de archivo o activo de este equipo.  Obtenga más información sobre el archivado de Teams en el [archivo o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **GROUPID** : el GROUPID exclusivo del grupo de respaldo de la oficina de 365
- **Clasificación** : la clasificación (si se usa en su organización) asignada al grupo de copia de seguridad de Office 365.  Obtenga más información acerca de las clasificaciones en [crear clasificaciones para los grupos de Office de su organización](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **Descripción** : la descripción establecida para el grupo de copia de seguridad de Office 365

### <a name="search"></a>Búsqueda

La búsqueda es compatible actualmente con la cadena "comienza con" y busca en el campo de **nombre de equipo** .

### <a name="edit"></a>Editar

Puede editar la configuración específica del grupo y del equipo seleccionando un equipo de la cuadrícula y seleccionando el botón **Editar** .

![Captura de pantalla de las opciones de editar equipo](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>Perfil de equipo

Puede ir a la página de Perfil de equipo de cualquier equipo desde la cuadrícula de información general de equipos principales haciendo clic en el nombre del equipo. En la página Perfil de equipo se muestran los miembros, los propietarios y los invitados que pertenecen al equipo (y su grupo de O365 que respalda), así como los canales y la configuración del equipo. En la página Perfil de equipo, puede:

- Agregar o quitar miembros y propietarios.
- Agregar o quitar canales (tenga en cuenta que no puede quitar el canal general).
- Actualizar la configuración del equipo y el grupo.
 
![Captura de pantalla de un perfil de equipo de ejemplo](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>Realizar cambios en los equipos

Puede cambiar los siguientes elementos de un equipo:
- **Usuarios del equipo** : puede Agregar o quitar miembros, y promover o disminuir el nivel de propietarios.
- **Canales** : puede Agregar canales nuevos o quitar los canales existentes.  No puedes eliminar el canal "general" predeterminado y, una vez que lo hayas creado, solo podrás modificar el nombre del canal, no una descripción.
- **Nombre del equipo**
- **Descripción del equipo**
- **Privacidad del equipo** : pública o privada
- **Clasificación de equipo** : respaldado por las clasificaciones de grupo de Office 365
- **Configuración de miembro del equipo** : seleccionar configuración de miembro del equipo

## <a name="other-supported-changes-to-teams"></a>Otros cambios admitidos en los equipos

- **Eliminar** : la eliminación de un equipo es una eliminación parcial del equipo y del grupo de Office 365 correspondiente.  Para restaurar un equipo eliminado por error, siga las instrucciones de [restaurar un grupo de Office 365 eliminado](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).
- **Archivo** : archivar un equipo pone el equipo en modo de solo lectura dentro de Microsoft Teams.  Como administrador, puede archivar y desarchivar Teams en nombre de su organización a través del portal de administración.


Se registran los cambios que realice en un equipo. Si va a modificar la configuración del grupo (cambiar el nombre, la descripción, la foto, la privacidad, la clasificación o los miembros del equipo), estos cambios se le atribuyen a través de la canalización de auditoría. Si va a realizar acciones con la configuración específica de Teams, se hará un seguimiento de los cambios y se les atribuye en el canal general del equipo.

## <a name="troubleshooting"></a>Solución de problemas

**Problema: falta Teams en la cuadrícula de información general de equipo**

Al entrar en el centro de administración de Microsoft Teams **** , en la opción de Teams, algunos de sus equipos no aparecen en la lista de la cuadrícula de información general de Teams.

**Causa**: este problema se produce cuando el sistema no ha sobrearchivado (o todavía no ha sido creado por el equipo), lo que puede llevar a que falte una propiedad para que lo reconozca.

**Solución: establezca manualmente la propiedad en el valor correcto a través de MS Graph.**

Reemplace **{GROUPID}** en la consulta del GROUPID real en cuestión, que puede obtener a través de Exchange Online PowerShell, con el cmdlet **"[Get-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** , como el atributo "**ExternalDirectoryObjectId**".

1. [Explorador de gráficos](https://developer.microsoft.com/en-us/graph/graph-explorer) de Access

2. Iniciar sesión en el explorador de gráficos en el menú de la izquierda

3. Cambiar la línea de consulta a: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. Agregue el valor siguiente en el cuerpo de la solicitud: {"resourceProvisioningOptions": ["Team"]}

5. Ejecute la consulta en la parte superior derecha.

6. Confirmar que el equipo aparece correctamente en el centro de administración de Microsoft Teams: información general del equipo


## <a name="learn-more"></a>Más información

[Referencia del cmdlet de Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Roles de administrador en Microsoft Teams](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

