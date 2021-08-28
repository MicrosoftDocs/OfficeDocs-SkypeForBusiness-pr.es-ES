---
title: Crear perfiles de directiva de ancho de banda en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Cree o modifique directivas de ancho de banda, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.
ms.openlocfilehash: 4ba24c7f1fa170386e6d74fc34ef99e580d5ac91
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583214"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Crear perfiles de directiva de ancho de banda en Skype Empresarial Server 
 
Cree o modifique directivas de ancho de banda, que se usan Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server. 
  
Las directivas de ancho de banda definen limitaciones en el uso de ancho de banda para las modalidades de audio y vídeo en tiempo real. Las directivas de ancho de banda se aplican a los perfiles de directivabandwidth, que se pueden aplicar a varios sitios de red para el control de admisión de llamadas.
  
Para obtener instrucciones sobre los límites de ancho de banda que debe establecer en la implementación del CAC, vea [Plan for call admission control in Skype Empresarial Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
Las directivas de ejemplo creadas en el procedimiento siguiente definen límites para el tráfico de audio global, sesiones de audio individuales, el tráfico de vídeo global y sesiones de vídeo individuales. Por ejemplo, el perfil de directiva de ancho de banda 5Mb_Link define los límites siguientes: 
  
- Límite de audio: 2.000 kbps
    
- Límite de sesión de audio: 200 kbps
    
- Límite de vídeo: 1.400 kbps
    
- Límite de sesión de vídeo: 700 kbps
    
> [!NOTE]
> El valor de Límite de sesión de audio es 40 kbps. El valor de Límite de sesión de vídeo es 100 kbps. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Para crear perfiles de directiva de ancho de banda mediante Skype Empresarial Server Shell de administración

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
2. Para cada perfil de directiva de ancho de banda que quiera crear, ejecute el cmdlet New-CsNetworkBandwidthPolicyProfile. Por ejemplo, ejecute lo siguiente:
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Para crear perfiles de directiva de ancho de banda mediante Skype Empresarial Server Panel de control

1. Abra Skype Empresarial Server Panel de control.
    
2. En la barra de navegación izquierda, haga clic en **Configuración de red**.
    
3. Haga clic en el botón de navegación **Perfil de directiva**.
    
4. Haga clic en **Nuevo**.
    
5. En la página **Nuevo perfil de directiva**, haga clic en **Nombre** y escriba un nombre para el perfil de directiva de ancho de banda.
    
6. Haga clic en **Límite de audio** y escriba el número máximo de kbps que permitir para todas las sesiones de audio combinadas.
    
7. Haga clic en **Límite de sesión de audio** y escriba el número máximo de kbps que permitir para cada sesión de audio.
    
8. Haga clic en **Límite de vídeo** y escriba el número máximo de kbps que permitir para todas las sesiones de vídeo combinadas.
    
9. Haga clic en **Límite de sesión de vídeo** y escriba el número máximo de kbps que permitir para cada sesión de vídeo.
    
10. Si lo desea, haga clic en **Descripción** y escriba información adicional para describir este perfil de directiva de ancho de banda.
    
11. Haga clic en **Confirmar**.
    
12. Para terminar de crear perfiles de directiva de ancho de banda para su topología, repita los pasos del 4 al 11 con la configuración para otros perfiles de directiva de ancho de banda.
    
## <a name="see-also"></a>Consulte también

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)