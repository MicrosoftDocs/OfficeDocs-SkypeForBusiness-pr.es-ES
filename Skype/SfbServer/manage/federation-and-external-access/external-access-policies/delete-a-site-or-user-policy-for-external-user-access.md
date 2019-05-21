---
title: Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Puede eliminar cualquier sitio o Directiva de usuario que aparezca en el panel de control de Skype empresarial Server en la página Directiva de acceso externo.
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280127"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos

Si ha creado o configurado directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:

  - Elimine cualquier sitio o Directiva de usuario que haya creado.

  - Restablecer la configuración predeterminada de la directiva global. La configuración de directiva global predeterminada deniega el acceso de usuarios externos. No se puede eliminar la directiva global.


Puede eliminar cualquier sitio o Directiva de usuario que aparezca en el panel de control de Skype empresarial Server en la página **Directiva de acceso externo** . Eliminar la directiva global no la elimina realmente, pero solo la restablece a la configuración predeterminada, que no incluye compatibilidad con ninguna de las opciones de acceso de usuarios externos. Para obtener más información sobre cómo restablecer la directiva global, vea [restablecer la directiva global para el acceso de usuarios externos](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para eliminar un sitio o una directiva de usuario para el acceso de usuarios externos

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  Haga clic en **acceso externo de usuarios**, haga clic en **Directiva de acceso externo**.

4.  En la pestaña **Directiva de acceso externo** , haga clic en el sitio o la Directiva de usuario que desea eliminar, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.

5.  Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Quitar directivas de PIN mediante cmdlets de Windows PowerShell

Las directivas de acceso externo se pueden eliminar mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Para quitar una directiva de acceso externo específica

  - Este comando quita la Directiva de acceso externo aplicada al sitio de Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para quitar todas las directivas de acceso externo que se aplican al ámbito de cada usuario

  - Este comando quita todas las directivas de acceso externo configuradas en el ámbito de cada usuario:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para quitar todas las directivas de acceso externas donde el acceso de usuarios externos está deshabilitado

  - Este comando elimina todas las directivas de acceso externas donde se ha deshabilitado el acceso de usuarios externos:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
