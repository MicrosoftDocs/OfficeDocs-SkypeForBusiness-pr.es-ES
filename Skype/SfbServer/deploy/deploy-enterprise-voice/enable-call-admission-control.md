---
title: Habilitar el control de admisión de llamadas en Skype Empresarial Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilite el control de admisión de llamadas Skype Empresarial Server Telefonía IP empresarial.
---

# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Habilitar el control de admisión de llamadas en Skype Empresarial Server
 
Habilite el control de admisión de llamadas Skype Empresarial Server Telefonía IP empresarial. 
  
Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Para habilitar el control de admisión de llamadas mediante Skype Empresarial Server Shell de administración

1. Inicie el Shell Skype Empresarial Server administración: haga clic en **Inicio, todos** los **programas,** **Skype Empresarial 2015** y, a continuación, haga clic **en Skype Empresarial Server Shell de administración**.
    
2. Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Si desea deshabilitar el CAC en la red, ejecute lo siguiente:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Para habilitar el control de admisión de llamadas mediante Skype Empresarial Server Panel de control

1. Abra Skype Empresarial Server Panel de control.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Global**.
    
4. Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Edición**.
    
5. En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.
    
    > [!NOTE]
    > Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla. 
  
6. Haga clic en **Confirmar**. 
    
## <a name="see-also"></a>Vea también

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)