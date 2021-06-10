---
title: Administrar equipos en el Centro de administración de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: Obtenga información acerca de cómo ver o actualizar los equipos que su organización ha configurado para colaboración en el centro de administración de Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237546"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>Administrar equipos en el Centro de administración de Microsoft Teams
==========================================

## <a name="overview"></a>Información general

Este artículo proporciona una descripción general de las herramientas de administración para equipos en el centro de administración de Microsoft Teams.

Como administrador, es posible que tenga que ver o actualizar los equipos que la organización configuró para la colaboración, o es posible que tenga que llevar a cabo acciones de corrección, como la asignación de propietarios a equipos sin propietario. Puede administrar los equipos que se usan en la organización tanto en el módulo de PowerShell para Microsoft Teams como en el centro de administración de Microsoft Teams. Puede acceder al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> . Para obtener todas las funciones de administración con estos dos conjuntos de herramientas, debe asegurarse de que tiene asignado uno de los roles siguientes:

- Administrador global
- Administrador de Teams

Puede obtener más información acerca de los roles de administrador en Teams en [Usar los roles de administrador de Microsoft Teams para administrar equipos](using-admin-roles.md) y puede ver más sobre cómo usar los cmdlets de PowerShell para administrar equipos en la [referencia de cmdlets de Microsoft Teams](/powershell/teams/?view=teams-ps).



## <a name="teams-overview-grid"></a>Información general de equipos

Las herramientas de administración para equipos se encuentran en el nodo **Equipos** en el centro de administración de Microsoft Teams. (En el centro de administración, seleccione **Teams**  >  **Administrar equipos).)** Cada equipo está a Microsoft 365 grupo y este nodo proporciona una vista de los grupos que se Microsoft Teams habilitados en su organización.

![Captura de pantalla de la cuadrícula de información general de equipos](media/manage-teams-in-modern-portal-grid.png)  

La cuadrícula muestra las siguientes propiedades:

- **Nombre del equipo**
- **Canales**: es el número de todos los canales del equipo, incluido el canal General predeterminado.
- **Miembros del equipo**: un recuento de los usuarios totales, incluidos los propietarios, los invitados y los miembros de su espacio empresarial.
- **Propietarios**: un recuento de propietarios de este equipo.
- **Invitados**: recuento de usuarios invitados de B2B de Azure Active Directory que son miembros de este equipo.
- **Privacidad:** visibilidad/AccessType del grupo de Microsoft 365 copia de seguridad.
- **Estado**: el estado Archivado o Activo de este equipo. Obtenga más información sobre archivar equipos en [Archivar o restaurar un equipo](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).
- **Descripción:** la descripción del grupo de Microsoft 365 copia de seguridad.
- **Clasificación:** la clasificación (si se usa en su organización) asignada al grupo de Microsoft 365 copia de seguridad. Obtenga más información sobre las clasificaciones en [Crear clasificaciones para los grupos de Office de su organización](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).
- **GroupID:** el id. de grupo único del grupo Microsoft 365 copia de seguridad.

> [!NOTE]
> Si no ve todas estas propiedades en la cuadrícula, haga clic en el icono **Editar columnas**. En el panel **Editar columnas**, puede usar el botón de alternancia para activar o desactivar columnas en la cuadrícula. Cuando haya terminado, haga clic en **Aplicar**.

### <a name="add"></a>Agregar

Para agregar un nuevo equipo, haga clic en **Agregar**. En el panel **Agregar un nuevo equipo**, otorgue un nombre y una descripción al equipo, indique si quiere convertirlo en un equipo público o privado y establezca la clasificación.

> [!NOTE]
> Los equipos recién creados se pueden administrar inmediatamente en el Centro de administración de Teams, a diferencia de la experiencia de otros clientes como, por ejemplo, Outlook.

### <a name="edit"></a>Editar 

Para editar configuraciones específicas de grupo y de equipo, seleccione el equipo haciendo clic a la izquierda del nombre de equipo y seleccione **Editar**.

### <a name="archive"></a>Archivar

Puede archivar un equipo. El archivado de un equipo convierte el equipo en modo de solo lectura en Teams. Como administrador, puede archivar y desarchivar equipos en nombre de su organización en el centro de administración. 

### <a name="delete"></a>Eliminar

Eliminar un equipo es una eliminación suave del equipo y el grupo Microsoft 365 correspondiente. Para restaurar un equipo eliminado por error, siga las instrucciones de [Restaurar un grupo eliminado.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="search"></a>Buscar 

La búsqueda admite la cadena "Empieza por" y busca en el campo **Nombre del grupo**.

## <a name="team-profile"></a>Perfil de equipo

Puede ir a la página de perfil de equipo de cualquier equipo desde la cuadrícula principal de información general de equipos al hacer clic en el nombre del equipo. La página de perfil del equipo muestra los miembros, propietarios e invitados que pertenecen al equipo (y su respaldo Microsoft 365 grupo), así como los canales y la configuración del equipo. En la página de perfil de equipo, puede:

- Agregar o quitar miembros y propietarios.
- Agregar o quitar canales (tenga en cuenta que no se puede quitar el canal General).
- Cambiar la configuración de grupo y equipo.
 
![Captura de pantalla de un perfil de equipo de ejemplo](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>Realizar cambios en los equipos

En la página de perfil del equipo, puede cambiar los siguientes elementos de un equipo:

- **Miembros**: agregue o elimine miembros y aumente o disminuya el nivel de los propietarios.
- **Canales**: agregue nuevos canales, y edite o elimine canales existentes. Recuerde que no puede eliminar el canal General predeterminado.
- **Nombre del equipo**
- **Descripción**
- **Privacidad**: establezca si el equipo es público o privado.
- **Clasificación:** esto está a Microsoft 365 clasificaciones de grupo. Elija **Confidencial**, **Extremadamente confidencial** o **General**.
- **Configuración de conversaciones**: establezca si los miembros pueden editar y eliminar los mensajes enviados.
- **Configuración de canales**: establezca si los miembros pueden crear nuevos canales y editar los existentes, y agregar, editar y quitar fichas, conectores y aplicaciones.

Los cambios realizados en un equipo se registran. Si va a modificar la configuración de un grupo (cambiar el nombre, la descripción, la foto, la privacidad, la clasificación o los miembros del equipo), los cambios se le atribuyen en la canalización de auditoría. Si lleva a cabo acciones en configuraciones específicas de Teams, se realiza un seguimiento de los cambios y se le atribuyen en el canal General del equipo.

## <a name="troubleshooting"></a>Solución de problemas

**Problema: faltan equipos en la cuadrícula de información general de equipo**

Algunos de los equipos no están en la lista de equipos de la cuadrícula información general de equipos.

**Causa**: este problema se produce cuando el sistema ha creado el perfil del equipo de forma incorrecta (o aún no se ha completado), lo que puede provocar que falte alguna propiedad para que se reconozca.

**Resolución: configure manualmente la propiedad en el valor correcto mediante MS Graph**

Reemplace **{groupid}** en la consulta para el GroupId real en cuestión, que puede obtener mediante el PowerShell de Exchange Online con el cmdlet **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"**, como el atributo "**ExternalDirectoryObjectId**".

1. Acceder a [Probador de Graph](https://developer.microsoft.com/graph/graph-explorer).

2. Inicie sesión en el Probador de Graph en el menú de la izquierda.

3. Cambie la línea de consulta a: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.

4. Agregue el siguiente valor en el cuerpo de la solicitud: {"resourceProvisioningOptions": ["Team"]}.

5. Ejecute la consulta en la parte superior derecha.

6. Confirme que el equipo se muestra correctamente en el centro de administración de Microsoft Teams: información general de equipo.

## <a name="learn-more"></a>Más información

- [Referencia de cmdlet para Teams](/powershell/teams/?view=teams-ps)  
- [Usar roles de administrador de Teams para administrar equipos](using-admin-roles.md)
- [Plan para la administración del ciclo de vida en Teams](plan-teams-lifecycle.md)