---
title: Habilitar control de admisión de llamadas en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilitar control de admisión de llamadas en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 1a9e719e6c008fcd8bf8c12612f8eea15447648e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009711"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Habilitar control de admisión de llamadas en Skype para Business Server
 
Habilitar control de admisión de llamadas en Skype para Business Server Enterprise Voice. 
  
Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Para habilitar el control de admisión de llamadas mediante el uso de Skype para Shell de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Si desea deshabilitar el CAC en la red, ejecute lo siguiente:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Para habilitar el control de admisión de llamadas mediante el uso de Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Global**.
    
4. Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Editar**.
    
5. En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.
    
    > [!NOTE]
    > Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla. 
  
6. Haga clic en **Confirmar**. 
    
## <a name="see-also"></a>Vea también

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)