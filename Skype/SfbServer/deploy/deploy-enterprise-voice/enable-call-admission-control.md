---
title: Habilitar el control de admisión de llamadas en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilite el control de admisión de llamadas en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 9ea8b03b48827abbb73e3d6e93ffb88ab93ad1ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831020"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Habilitar el control de admisión de llamadas en Skype Empresarial Server
 
Habilite el control de admisión de llamadas en Skype Empresarial Server Telefonía IP empresarial. 
  
Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Para habilitar el control de admisión de llamadas mediante el Shell de administración de Skype Empresarial Server

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**
    
2. Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Si desea deshabilitar el CAC en la red, ejecute lo siguiente:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Para habilitar el control de admisión de llamadas mediante el Panel de control de Skype Empresarial Server

1. Abra el Panel de control de Skype Empresarial Server.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Global**.
    
4. Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Edición**.
    
5. En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.
    
    > [!NOTE]
    > Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla. 
  
6. Haga clic en **Confirmar**. 
    
## <a name="see-also"></a>Vea también

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
