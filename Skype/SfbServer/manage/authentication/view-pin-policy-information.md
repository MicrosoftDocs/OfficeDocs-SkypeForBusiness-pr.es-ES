---
title: Ver información de directivas de PIN en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumen: vea la información de la Directiva de PIN de un usuario para Skype empresarial Server.'
ms.openlocfilehash: 57a54e960a0c89408f173567a78449cad21de9ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818702"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Ver información de directivas de PIN en Skype empresarial Server
 
**Resumen:** Ver la información de la Directiva de PIN de un usuario para Skype empresarial Server.
  
Puede usar la pestaña **Directiva de PIN** para ver la autenticación del número de identificación personal (PIN) de los usuarios que se conectan a Skype empresarial con teléfonos IP. Para utilizar la autenticación de PIN, asegúrese de que la opción **Habilitar autenticación PIN** esté seleccionada en la configuración del servicio web.
  
Siga estos pasos para modificar una directiva de PIN de nivel de usuario o de sitio. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Para ver información sobre una directiva de PIN en el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Skype empresarial Server. .
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.
    
4. En la página **Directiva de PIN**, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Visualización de directivas de PIN con cmdlets de Windows PowerShell

También puede ver directivas de PIN con Windows PowerShell y el cmdlet Get-CsPinPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.
  
### <a name="to-view-pin-policies"></a>Para ver las directivas de PIN

Para ver información sobre todas las directivas de PIN, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
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

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>Vea también

[Crear una nueva Directiva de PIN en Skype empresarial Server](create-a-new-pin-policy.md)
