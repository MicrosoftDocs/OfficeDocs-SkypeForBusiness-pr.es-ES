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
ms.localizationpriority: medium
description: No puede eliminar completamente una directiva global. El uso **de la opción** Eliminar de la directiva global solo restablece la directiva global a la configuración predeterminada, que no incluye compatibilidad con ninguna opción de acceso de usuario externo.
ms.openlocfilehash: 316e0dab6004c3f4b5d07e8428215b4cc0f2deab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621056"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Restablecer la directiva global para el acceso de usuarios externos en Skype Empresarial Server 

Si ha creado o configurado directivas de acceso de usuarios externos que ya no desea usar, puede usar los siguientes métodos:

  - Elimine cualquier directiva de usuario o sitio que haya creado.

  - Restablezca la configuración predeterminada de la directiva global. La configuración global predeterminada deniega cualquier tipo de acceso de usuarios externos. La directiva global no se puede eliminar.

No puede eliminar completamente una directiva global. La **opción Eliminar** de la directiva global solo restablece la directiva global a la configuración predeterminada, que no incluye compatibilidad con ninguna opción de acceso de usuario externo.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para restablecer la directiva global según la configuración predeterminada

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins o tenga derechos de usuario equivalentes, o que esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.

3.  En la barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y en **Directiva de acceso externo**.

4.  En la ficha **Directiva de acceso externo**, haga clic en la directiva global, haga en **Editar** y, a continuación, haga clic en **Eliminar**.

5.  Cuando se le solicite confirmar la eliminación, haga clic en **Aceptar**. Aparecerá un mensaje en la parte superior de la página donde se le comunica que la directiva global se ha restablecido.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Restablecer la directiva de acceso externo global mediante Windows PowerShell cmdlets

La directiva de acceso externo global se puede restablecer mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy. Puede ejecutar este cmdlet desde el Shell Skype Empresarial Server de administración o desde una sesión remota Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para restablecer la directiva de acceso externo global

  - Este comando restablece la directiva de acceso externo global:<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

Para obtener más información, vea el tema de ayuda del cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)
