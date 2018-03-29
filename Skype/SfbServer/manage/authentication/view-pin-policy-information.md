---
title: Ver información de directivas de PIN de Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumen: Ver información de directiva del NIP de un usuario de Skype para Business Server 2015.'
ms.openlocfilehash: 3b62dae5cbd29c4622e30c6369a498eb48e126c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-pin-policy-information-in-skype-for-business-server-2015"></a>Ver información de directivas de PIN de Skype Empresarial Server 2015
 
**Resumen:** Ver información de directiva del NIP de un usuario de Skype para Business Server 2015.
  
Puede utilizar la ficha **Directiva de NIP** para ver identificación personal numérico (PIN) autenticación de usuarios que se conectan a Skype para el negocio con los teléfonos IP. Para usar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación de PIN** esté seleccionada en la configuración del servicio web.
  
Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para ver información acerca de una directiva de NIP en Skype para Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Directivas de NIP de visualización mediante Cmdlets de Windows PowerShell

También puede ver directivas de NIP mediante Windows PowerShell y el cmdlet Get-CsPinPolicy. Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-view-pin-policies"></a>Para ver las directivas de PIN

Para ver información acerca de todas las directivas PIN, escriba el comando siguiente en el Skype para el Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:
    
  ```
  Get-CsPinPolicy
  ```

Devolverá información similar a la siguiente:

  ```
  Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>Vea también

#### 

[Crear una nueva directiva de NIP en Skype para Business Server 2015](create-a-new-pin-policy.md)

