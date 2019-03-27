---
title: Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede eliminar cualquier directiva de sitio o de usuario que aparece en el Skype para el Panel de Control de Business Server en la página Directiva de acceso externo.
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889807"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos

Si ha creado o configurado las directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:

  - Elimine cualquier directiva de sitio o de usuario que ha creado.

  - Restablecer la directiva global para la configuración predeterminada. La configuración de la directiva global predeterminada denegar el acceso de los usuarios externos. No se puede eliminar la directiva global.


Puede eliminar cualquier directiva de sitio o de usuario que aparece en el Skype para el Panel de Control de Business Server en la página **Directiva de acceso externo** . Eliminación de la directiva global, no elimina realmente, pero sólo restablece la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos. Para obtener más información acerca del restablecimiento de la directiva global, consulte [Restablecer la directiva global para el acceso de usuarios externos](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para eliminar una directiva de sitio o usuario para el acceso de usuarios externos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  Haga clic en **Acceso de usuarios externos**, haga clic en **Directiva de acceso externo**.

4.  En la ficha **Directiva de acceso externo** , haga clic en la directiva de sitio o usuario que desea eliminar, haga clic en **Editar**y, a continuación, haga clic en **Eliminar**.

5.  Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Eliminación de directivas de PIN mediante el uso de Cmdlets de Windows PowerShell

Directivas de acceso externo se pueden eliminar mediante el uso de Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Para quitar una directiva de acceso externo determinada

  - Este comando quita la directiva de acceso externo aplicada al sitio de Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para quitar todas las externos obtener acceso a las directivas que se aplican al ámbito por usuario

  - Este comando quita todas las directivas de acceso externo configuradas en el ámbito por usuario:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para quitar todas las directivas de acceso externo donde se deshabilita el acceso de usuarios externos

  - Este comando elimina todas las directivas de acceso externo donde usuarios externos acceso se ha deshabilitado:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
