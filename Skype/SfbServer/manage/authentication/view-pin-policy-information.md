---
title: Ver información de directiva de PIN en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumen: vea la información de directiva de PIN de un usuario para Skype Empresarial Server.'
ms.openlocfilehash: fca606d00507f199e09d84604d60cc8004ad9a9b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013734"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Ver información de directiva de PIN en Skype Empresarial Server
 
**Resumen:** Ver la información de directiva de PIN de un usuario para Skype Empresarial Server.
  
Puede usar la pestaña Directiva de **PIN** para ver la autenticación de número de identificación personal (PIN) de los usuarios que se conectan a Skype Empresarial con teléfonos IP. Para usar la autenticación PIN, asegúrese de que la opción **Habilitar autenticación PIN** esté seleccionada en la configuración del servicio web.
  
Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para ver información sobre una directiva de PIN en el Panel de control de Skype Empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Visualización de directivas de PIN mediante Windows PowerShell cmdlets

También puede ver directivas de PIN mediante Windows PowerShell y el cmdlet Get-CsPinPolicy. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso Windows PowerShell para conectarse a Skype Empresarial Server, vea [Administración remota de PowerShell de Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-view-pin-policies"></a>Para ver directivas de PIN

Para ver información sobre todas las directivas de PIN, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
  ```PowerShell
  Get-CsPinPolicy
  ```

Devolverá información similar a la siguiente:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Para obtener más información, vea el tema de ayuda del cmdlet [Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Vea también

[Crear una nueva directiva de PIN en Skype Empresarial Server](create-a-new-pin-policy.md)