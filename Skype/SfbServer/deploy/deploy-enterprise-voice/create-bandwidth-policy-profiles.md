---
title: Crear perfiles de directivas de ancho de banda en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Crear o modificar directivas de ancho de banda, que se usan por el control de admisión de llamadas de Enterprise Voice en Skype para Business Server.
ms.openlocfilehash: 51516e07a75cc4239d89310c9d33194a225b3a02
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500593"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server-2015"></a>Crear perfiles de directivas de ancho de banda en Skype Empresarial Server 2015
 
Crear o modificar directivas de ancho de banda, que se usan por el control de admisión de llamadas de Enterprise Voice en Skype para Business Server. 
  
Las directivas de ancho de banda definen las limitaciones de uso de ancho de banda para modalidades de vídeo y de audio en tiempo real. Las directivas de ancho de banda son perfiles de directiva aplicada tobandwidth, que se pueden aplicar a varios sitios de red para el control de admisión de llamadas.
  
Para obtener instrucciones sobre los límites de ancho de banda de qué se debe definir en su implementación de CAC, consulte [Plan para el control de admisión de llamadas en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
Las directivas de ejemplo creadas en el procedimiento siguiente definen límites para el tráfico de audio global, sesiones de audio individuales, el tráfico de vídeo global y sesiones de vídeo individuales. Por ejemplo, el perfil de directiva de ancho de banda 5Mb_Link define los límites siguientes: 
  
- Límite de audio: 2.000 kbps
    
- Límite de sesión de audio: 200 kbps
    
- Límite de vídeo: 1.400 kbps
    
- Límite de sesión de vídeo: 700 kbps
    
> [!NOTE]
> El valor de Límite de sesión de audio es 40 kbps. El valor de Límite de sesión de vídeo es 100 kbps. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Para crear perfiles de directiva de ancho de banda mediante Skype de consola de administración de servidor empresarial

1. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
2. Para cada perfil de directiva de ancho de banda que quiera crear, ejecute el cmdlet New-CsNetworkBandwidthPolicyProfile. Por ejemplo, ejecute lo siguiente:
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Para crear perfiles de directiva de ancho de banda mediante Skype para el Panel de Control de servidor empresarial

1. Abra Skype para el Panel de Control de servidor empresarial.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Perfil de directiva**.
    
4. Haga clic en **Nuevo**.
    
5. En la página **Nuevo perfil de directiva**, haga clic en **Nombre** y escriba un nombre para el perfil de directiva de ancho de banda.
    
6. Haga clic en **Límite de audio** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de audio combinadas.
    
7. Haga clic en **Límite de sesión de audio** y escriba el número máximo de kbps que se deben permitir para cada sesión de audio.
    
8. Haga clic en **Límite de vídeo** y escriba el número máximo de kbps que se deben permitir para todas las sesiones de vídeo combinadas.
    
9. Haga clic en **Límite de sesión de vídeo** y escriba el número máximo de kbps que se deben permitir para cada sesión de vídeo.
    
10. Si lo desea, haga clic en **Descripción** y escriba información adicional para describir este perfil de directiva de ancho de banda.
    
11. Haga clic en **Confirmar**.
    
12. Para terminar de crear perfiles de directiva de ancho de banda para su topología, repita los pasos del 4 al 11 con la configuración para otros perfiles de directiva de ancho de banda.
    
## <a name="see-also"></a>Vea también

[Nueva CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)