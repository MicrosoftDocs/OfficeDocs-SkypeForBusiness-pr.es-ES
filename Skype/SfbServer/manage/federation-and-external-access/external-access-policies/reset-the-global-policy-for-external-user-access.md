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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Completamente, no se puede eliminar una directiva global. Con la opción **Eliminar** en la directiva global, sólo restablece la directiva global para la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.
ms.openlocfilehash: c2f938219a35de97088c26f81d9d59e46e799ebb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33923177"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Restablecer la directiva global para el acceso de usuarios externos en Skype para Business Server 

Si ha creado o configurado las directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:

  - Elimine cualquier directiva de sitio o de usuario que ha creado.

  - Restablecer la directiva global para la configuración predeterminada. La configuración de la directiva global predeterminada denegar el acceso de los usuarios externos. No se puede eliminar la directiva global.

Completamente, no se puede eliminar una directiva global. Con la opción **Eliminar** en la directiva global, sólo restablece la directiva global para la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para restablecer la directiva global para la configuración predeterminada

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.

3.  En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**, haga clic en **Directiva de acceso externo**.

4.  En la ficha **Directiva de acceso externo** , haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Eliminar**.

5.  Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**. Aparece un mensaje en la parte superior de la página que le informa de que se ha restablecido la directiva global.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Restablecer la directiva de acceso externo Global mediante el uso de Cmdlets de Windows PowerShell

La directiva de acceso externo global se puede restablecer mediante el uso de Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para restablecer la directiva de acceso externo global

  - Este comando restablece la directiva de acceso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Para obtener más información, vea el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


