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
description: Habilite el control de admisión de llamadas Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 65c9ea2e4732ca4c2c069479826f353a9a2dabf82d6eee35c6feaf1c14391ddd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281203"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Habilitar el control de admisión de llamadas en Skype Empresarial Server
 
Habilite el control de admisión de llamadas Skype Empresarial Server Telefonía IP empresarial. 
  
Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Para habilitar el control de admisión de llamadas mediante Skype Empresarial Server Shell de administración

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
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
    
## <a name="see-also"></a>Consulte también

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)