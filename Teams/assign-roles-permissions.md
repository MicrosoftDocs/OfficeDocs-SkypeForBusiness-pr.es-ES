---
title: "Asignar roles y permisos en Microsoft Teams | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Sepa cómo asignar roles y permisos de propietario y miembro de equipo en Microsoft Teams, incluidos permisos para crear equipos."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 0fb84f0b72d2d36f3a584e811fa8640159825429
ms.sourcegitcommit: cd6f4ac2ee7fa2b9de7af5c75c914eb84468d8f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>Asignar roles y permisos en Microsoft Teams
===============================================

Dentro de Microsoft Teams hay dos roles: **Propietario** y **Miembro**. De forma predeterminada, el usuario que crea un equipo tiene el estado Propietario. Si se crea un equipo a partir de un grupo de Office 365 existente, los permisos se heredan.

En la tabla siguiente se muestra la diferencia entre un propietario y un miembro:

|  |Propietario de equipo  |Miembro de equipo  |
|---------|---------|---------|
|**Crear equipo**     |Sí        |No         |
|**Abandonar equipo**     |Sí         |Sí         |
|**Editar nombre o descripción del equipo**      |Sí         |No         |
|**Eliminar equipo**      |Sí         |No         |
|**Agregar canal**      |Sí         |Sí*         |
|**Editar nombre o descripción del canal**      |Sí         |Sí*         |
|**Eliminar canal**      |Sí         |Sí*         |
|**Agregar miembros**      |Sí         |No         |
|**Agregar fichas**      |Sí         |Sí*         |
|**Agregar conectores**      |Sí         |Sí*         |
|**Agregar bots**      |Sí         |Sí*         |
\* Un propietario puede desactivar estos elementos a nivel de equipo, en cuyo caso, los miembros no tendrían acceso a ellos.

\*\*Tras agregar un miembro a un equipo, un propietario también puede promover un miembro al estado Propietario. También es posible que un propietario disminuya su propio estado a Miembro.

| | |
|---------|---------|
|![Icono de bombilla.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image1.png) <br></br>Nota     |Los propietarios pueden establecer a otros miembros como propietarios en la opción Ver equipos. Un equipo puede tener hasta 100 propietarios. Se recomienda tener al menos unos cuantos propietarios para ayudar a gestionar el equipo. De este modo se evita que algunos grupos se queden huérfanos si el único propietario deja la organización. Si desea más información sobre los grupos huérfanos, consulte [Asignar un nuevo propietario a un grupo huérfano](https://support.office.com/en-us/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).        |

<a name="permissions-to-create-teams"></a>Permisos para crear equipos
---------------------------

De manera predeterminada, todos los usuarios que tengan una casilla de correo en Exchange Online tienen permisos para crear grupos de Office 365 y, por lo tanto, para crear equipos dentro de Microsoft Teams. Puede ejercer un control más estricto y restringir la creación de nuevos equipos y, por lo tanto, la creación de grupos de Office 365 si delega la creación de grupos y los derechos de administración en un conjunto de usuarios.

Si su organización está interesada en hacer esto, puede encontrar instrucciones sobre las tareas que se deben realizar a continuación.

1.  Identifique o cree un grupo de seguridad de usuarios que tendrán permisos delegados para crear grupos de Office 365.

    a.  **Acción:** Establezca un grupo de seguridad en Office 365 para poder agregar usuarios que puedan crear grupos de Office 365.

    B. Para obtener más información, consulte [Crear, editar o eliminar un grupo de seguridad en el centro de administración de Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).

2.  Compruebe que está habilitado el control de toda la empresa para que los usuarios creen grupos.

    a.  **Acción:** Ejecute el siguiente script de PowerShell y compruebe que el parámetro UsersPermissiontoCreateGroupsEnabled esté establecido en **True**.

    Connect-MsolService

    Get-MsolCompanyInformation

    b.  Si no es verdadero, ejecute el cmdlet Set-MsolCompanySettings **para establecerlo en True**.
Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True

    c. Para obtener más información, consulte: [Administrar la creación de grupos de Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).

3.  Establecer la configuración de grupos de Office 365 para que solo los grupos de seguridad identificados tengan permisos para crear grupos

    a.  **Acción:** Cree un objeto de configuración de grupos que contenga las opciones de configuración del grupo al que se le asignarán permisos delegados para crear grupos. 

    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "false"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings

    b. Para obtener más información, consulte: [Administrar la creación de grupos de Office 365](https://support.office.com/en-us/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)


||||
|---------|---------|---------|
| ![Icono de Punto de decisión.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Punto de decisión         |¿Todos los usuarios de Microsoft Teams podrán crear equipos (recomendado)?         |
| ![Icono de Siguientes pasos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Siguientes pasos         |Modifique los permisos predeterminados que determinan quiénes pueden crear grupos de Office 365 si es necesario limitar los usuarios que pueden crear equipos.         |
