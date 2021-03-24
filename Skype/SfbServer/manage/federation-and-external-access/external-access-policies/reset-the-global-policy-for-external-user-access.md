---
title: Restablecer la directiva global para el acceso de usuarios externos
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: No se puede eliminar íntegramente una política global. Si se usa la opción **Eliminar** en la directiva global solamente se restablece la directiva global según la configuración predeterminada, que no incluye compatibilidad con opciones de acceso para usuarios externos.
ms.openlocfilehash: 6c74690d86f7a300b79b755db7c6111eec7810f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098976"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Restablecer la directiva global para el acceso de usuarios externos en Skype Empresarial Server 

Si ha creado o configurado directivas de acceso de usuarios externos que ya no desea usar, puede hacer lo siguiente:

  - Elimine cualquier directiva de usuario o sitio que haya creado.

  - Restablezca la configuración predeterminada de la directiva global. La configuración global predeterminada deniega cualquier tipo de acceso de usuarios externos. La directiva global no puede eliminarse.

No se puede eliminar íntegramente una política global. Si se usa la opción **Eliminar** en la directiva global solamente se restablece la directiva global según la configuración predeterminada, que no incluye compatibilidad con opciones de acceso para usuarios externos.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para restablecer la directiva global según la configuración predeterminada

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.

3.  En la barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Directiva de acceso externo**.

4.  En la ficha **Directiva de acceso externo**, haga clic en la directiva global, haga en **Editar** y, a continuación, haga clic en **Eliminar**.

5.  Cuando se le solicite confirmar la eliminación, haga clic en **Aceptar**. Aparecerá un mensaje en la parte superior de la página donde se le comunica que la directiva global se ha restablecido.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Restablecer la directiva de acceso externo global mediante Windows PowerShell cmdlets

La directiva de acceso externo global se puede restablecer mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para restablecer la directiva de acceso externo global

  - Este comando restablece la directiva de acceso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Para obtener más información, vea el tema de ayuda del cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)