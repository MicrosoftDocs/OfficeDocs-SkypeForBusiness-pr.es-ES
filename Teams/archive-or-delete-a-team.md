---
title: Archivar o borrar un equipo en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Obtenga información sobre cómo archivar o eliminar permanentemente un equipo.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdbc5a03698fc5aa8cd7d686ad0c3038132236f1
ms.sourcegitcommit: 21ef0846c8d9bc986550d34614bae1cb9eb2ded8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "36980580"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archivar o borrar un equipo en Microsoft Teams
===========================================

Con el tiempo, es posible que un equipo creado en Microsoft Teams se quede fuera de uso o que desee archivar o eliminar un equipo al final de un proyecto. Si es un administrador de Microsoft Teams, siga los pasos que se indican en este artículo para archivar o eliminar un equipo que ya no es necesario. Al archivar un equipo, se detiene toda la actividad de ese equipo, pero puede seguir agregando o quitando miembros y actualizando los roles y podrá seguir viendo toda la actividad del equipo en canales, archivos y chats. Al eliminar un equipo, también se elimina la actividad de equipo en los canales, los archivos y los chats relacionados.

> [!IMPORTANT]
> Los equipos archivados se pueden reactivar, pero no puede eliminar directamente un equipo que haya sido eliminado. Considere la posibilidad de archivar primero el equipo y posponer la eliminación hasta que esté seguro de que ya no lo necesita.

## <a name="archive-a-team"></a>Archivar un equipo

Siga estos pasos para archivar un equipo.

1. En el centro de administración de Microsoft Teams, seleccione **Teams**.
2. Seleccione un equipo haciendo clic en el nombre del equipo.
3. Seleccione **archivo**. Aparecerá el siguiente mensaje.

    ![Captura de pantalla del mensaje de archivo de Teams](media/teams-archive-message.png)

4. Si desea que el sitio de SharePoint para el equipo sea de solo lectura, active la casilla.
5. Seleccione **archivar** para archivar el equipo. El estado del equipo cambiará a **archivado**.

## <a name="make-an-archived-team-active"></a>Activar un equipo archivado

Siga estos pasos para volver a activar un equipo archivado.

1. En el centro de administración de Microsoft Teams, seleccione **Teams**.
2. Seleccione un equipo haciendo clic en el nombre del equipo.
3. Seleccione **desarchivar**. El estado del equipo cambiará a **activo**.

## <a name="delete-a-team"></a>Eliminar un equipo

Si el equipo no se va a necesitar en el futuro, puede eliminarlo en lugar de archivarlo. Siga estos pasos para eliminar un equipo.

1.  En el centro de administración de Microsoft Teams, seleccione **Teams**.
2.  Seleccione un equipo haciendo clic en el nombre del equipo.
3.  Seleccione **eliminar**. Aparecerá un mensaje de confirmación.
4.  Seleccione **eliminar** para eliminar de forma permanente el equipo.

## <a name="restore-a-deleted-team"></a>Restaurar un equipo eliminado

Siga estos pasos para restaurar un equipo eliminado restaurando el grupo de Office 365 que está asociado con el equipo. De forma predeterminada, un grupo de Office 365 eliminado se conserva durante 30 días. Este período de 30 días se llama "eliminación de software" porque puede restaurar el grupo. Para obtener más información, consulte [restaurar un grupo eliminado de Office 365](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Instalar el módulo AzureADPreview

1. Abra Windows PowerShell como administrador.
2. Si tiene una versión anterior del módulo AzureADPreview instalada o el módulo AzureAD instalado, desinstálelo ejecutando una de las siguientes opciones:

    ``` 
    Uninstall-Module AzureADPreview
    ```

    ```
    Uninstall-Module AzureAD
    ```
3. Para instalar la versión más reciente del módulo AzureADPreview, ejecute lo siguiente:

    ```
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>Restaurar el grupo de 365 eliminado de Office

1. Conéctese a Azure AD ejecutando lo siguiente:
    ```
    Connect-AzureAD
    ```
    Cuando se le solicite, inicie sesión con su cuenta de administrador y su contraseña.  
2. Ejecute lo siguiente para mostrar una lista de todos los grupos de Office 365 eliminados temporalmente que siguen el período de retención de 30 días. Use el parámetro **-All $true** si tiene muchos grupos.
    ```
    Get-AzureADMSDeletedGroup
    ``` 
3. Busque el grupo que desea restaurar y, a continuación, anote el identificador.
4. Ejecute lo siguiente para restaurar el grupo, donde [id] es el identificador de grupo.
    ```
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Ejecute lo siguiente para comprobar que el grupo se ha restaurado correctamente, donde [id] es el identificador de grupo.
    ```
    Get-AzureADGroup -ObjectId [Id]
    ```

    Puede tardar hasta 24 horas en completarse el proceso de restauración, después del cual el equipo y el contenido asociados con el equipo, incluidas las fichas y los canales, se muestran en Teams.
