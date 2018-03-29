---
title: Habilitar el control de admisión de llamadas en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Habilitar el control de admisión de llamada en Skype para Business Server Telefonía IP empresarial.
ms.openlocfilehash: 52425dffc788ab2d1e6822957f30b67e00cb7a9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-admission-control-in-skype-for-business-server-2015"></a>Habilitar el control de admisión de llamadas en Skype Empresarial Server 2015
 
Habilitar el control de admisión de llamada en Skype para Business Server Telefonía IP empresarial. 
  
Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>Para habilitar el control de admisión de llamada mediante Skype de Shell de administración de servidor de Business

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Si desea deshabilitar el CAC en la red, ejecute lo siguiente:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>Para habilitar el control de admisión de llamada mediante Skype para Panel de Control de servidor empresarial

1. Abre Skype para Panel de Control del servidor de empresa.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Global**.
    
4. Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Editar**.
    
5. En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.
    
    > [!NOTE]
    > Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla. 
  
6. Haga clic en **Confirmar**. 
    
## <a name="see-also"></a>Vea también

#### 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Conjunto de CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Quitar CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)

