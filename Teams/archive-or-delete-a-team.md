---
title: Archivar o eliminar un equipo en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Obtenga información acerca de cómo archivar o eliminar permanentemente un equipo.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e065ddccd9781143b9c3522aa795f85ef0e118bb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780719"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archivar o eliminar un equipo en Microsoft Teams
===========================================

Con el tiempo, es posible que un equipo creado en Microsoft Teams se quede fuera de uso o que desee archivar o eliminar un equipo al final de un proyecto. Si es un administrador de Microsoft Teams, siga los pasos de este artículo para archivar o eliminar un equipo que ya no se necesita.

Cuando archiva un equipo, toda la actividad del equipo cesa. El archivado de un equipo también archiva canales privados en el equipo y sus colecciones de sitios asociadas.  Sin embargo, puede seguir agregando o quitando los miembros de, y aún podrá ver todas las actividades del equipo en canales, archivos y chats estándar y privados.

Al eliminar un equipo, se elimina también la actividad de equipo en canales estándar y privados (y colecciones de sitios asociadas), archivos y charlas.

> [!IMPORTANT]
> Los equipos archivados se pueden reactivar, pero no puede restaurar directamente un equipo que se ha eliminado. Considere la posibilidad de archivar el equipo en primer lugar y, a continuación, posponga la eliminación hasta que esté seguro de que ya no necesita el equipo.

## <a name="archive-a-team"></a>Archivar un equipo

Siga estos pasos para archivar un equipo.

1. En el centro de administración de Microsoft Teams, seleccione **Teams**.
2. Para que seleccione un equipo, haga clic en el nombre del equipo.
3. Seleccione **Archivo**. Aparecerá el siguiente mensaje.

    ![Captura de pantalla del mensaje del archivo de Teams](media/teams-archive-message.png)

4. Si desea que el sitio de SharePoint para el equipo sea de solo lectura, seleccione la casilla.
5. Seleccione **archivo** archivar el equipo. El estado del equipo cambiará a **Archivados**.

## <a name="make-an-archived-team-active"></a>Haga que un equipo archivado se active

Siga estos pasos para volver a activar un equipo archivado.

1. En el centro de administración de Microsoft Teams, seleccione **Teams**.
2. Para que seleccione un equipo, haga clic en el nombre del equipo.
3. Seleccione **Unarchivar**. El estado del equipo cambiará a **Activo**.

## <a name="delete-a-team"></a>Eliminar un equipo

Si el equipo no va a necesitar el futuro, puede eliminarlo en lugar de archivarlo. Para eliminar un grupo, siga estos pasos:

1.  En el centro de administración de Microsoft Teams, seleccione **Teams**.
2.  Para que seleccione un equipo, haga clic en el nombre del equipo.
3.  Seleccione **Eliminar**. Aparecerá un mensaje de confirmación.
4.  Seleccione **Eliminar** para eliminar permanentemente el equipo.

## <a name="restore-a-deleted-team"></a>Restaurar un equipo eliminado

Siga estos pasos para restaurar un equipo eliminado al restaurar el grupo de Office 365 que está asociado al equipo. Restaurando el grupo de Office 365 para un equipo, restaura el contenido del equipo, incluidas las pestañas, canales estándar y canales privados y sus colecciones de sitios asociadas.

De forma predeterminada, un grupo eliminado de Office 365 se conserva durante 30 días. Este periodo de 30 días se llama "eliminación parcial", ya que puede restaurar el grupo. Para obtener más información, consulte [restaurar un grupo eliminado de Office 365](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Instalar el módulo AzureADPreview

1. Abra Windows PowerShell como administrador.
2. Si tiene instalada una versión anterior del módulo AzureADPreview o el módulo AzureAD, desinstálela mediante la ejecución de uno de los siguientes procedimientos:

    ```PowerShell 
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. Para instalar la última versión del módulo AzureADPreview, ejecute lo siguiente:

    ```PowerShell
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>Restaurar el grupo de Office 365 eliminado

1. Para conectarse a Azure AD, ejecute lo siguiente:
    ```PowerShell
    Connect-AzureAD
    ```
    Cuando se le solicite, inicie sesión con su cuenta de administrador y su contraseña.  
2. Ejecute lo siguiente para mostrar una lista de todos los grupos de Microsoft 365 eliminados temporalmente que aún se encuentran en el período de retención de 30 días. Use el parámetro **-All $True** si tiene una gran cantidad de grupos.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. Busque el grupo que quiera restaurar y, después, tome nota de la ID.
4. Ejecute lo siguiente para restaurar el grupo, donde [id.] es el ID. de grupo.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Ejecute lo siguiente para comprobar si el grupo se ha restaurado correctamente, donde [id.] es el ID. de grupo.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Se pueden tardar hasta 24 horas en completarse el proceso de restauración, tras lo cual el equipo y el contenido asociados al equipo, incluidos pestañas y canales, se muestran en equipos.
