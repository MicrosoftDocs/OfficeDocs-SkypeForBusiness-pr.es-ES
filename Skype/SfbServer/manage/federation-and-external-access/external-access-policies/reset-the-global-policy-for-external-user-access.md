---
title: Restablecer la directiva global para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: No puede eliminar completamente una directiva global. El uso de la opción **eliminar** en la directiva global solo restablece la directiva global a la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818271"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Restablecer la directiva global para el acceso de usuarios externos en Skype empresarial Server 

Si ha creado o configurado directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:

  - Elimine cualquier sitio o Directiva de usuario que haya creado.

  - Restablecer la configuración predeterminada de la directiva global. La configuración de directiva global predeterminada deniega el acceso de usuarios externos. No se puede eliminar la directiva global.

No puede eliminar completamente una directiva global. El uso de la opción **eliminar** en la directiva global solo restablece la directiva global a la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para restablecer la configuración predeterminada de la directiva global

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.

3.  En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **Directiva de acceso externo**.

4.  En la pestaña **Directiva de acceso externo** , haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.

5.  Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**. En la parte superior de la página aparece un mensaje que le informa de que se ha restablecido la directiva global.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Restablecer la Directiva de acceso externo global mediante cmdlets de Windows PowerShell

La Directiva de acceso externo global se puede restablecer mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para restablecer la Directiva de acceso externo global

  - Este comando restablece la Directiva de acceso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


