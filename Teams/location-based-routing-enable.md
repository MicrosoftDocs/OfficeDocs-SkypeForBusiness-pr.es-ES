---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo habilitar el enrutamiento Location-Based para enrutamiento directo, lo que incluye habilitarlo para usuarios, sitios de red, configuraciones de puerta de enlace y directivas de llamada.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aadf5f4e4dff855d80c275be3d2027e767a732ad
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562199"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar enrutamiento basado en la ubicación para el enrutamiento directo

En este artículo se describe cómo habilitar el enrutamiento Location-Based para enrutamiento directo. Antes de seguir los pasos de este artículo, asegúrese de que ha leído [Planear el enrutamiento Location-Based para enrutamiento directo](location-based-routing-plan.md) y ha completado los pasos de Configurar las [opciones de red para el enrutamiento Location-Based](location-based-routing-configure-network-settings.md).

 Después de implementar el enrutamiento directo y configurar regiones, sitios y subredes de red, ya puede habilitar el enrutamiento de Location-Based. Para completar los pasos de este artículo, necesitará estar familiarizado con los cmdlets de PowerShell. Para obtener más información, consulte [Introducción a PowerShell de Teams](teams-powershell-overview.md)

 Debe habilitar Location-Based Enrutamiento para lo siguiente:

- Usuarios
- Sitios de red
- Configuraciones de puerta de enlace
- Directivas de llamada

Puede usar el [Centro de administración de Teams](#using-the-microsoft-teams-admin-center) o [PowerShell](#using-powershell) para habilitar el enrutamiento de Location-Based.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Habilitar el enrutamiento Location-Based para los usuarios

1. Cree una directiva de enrutamiento de voz y asigne los usos de RTC a la directiva. Al asignar usos de RTC a una directiva, asegúrese de realizar una de las siguientes acciones:

    - Use los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC local al sitio.

    - Use los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no son necesarias las restricciones de enrutamiento Location-Based.

2. Asigne la directiva de enrutamiento de voz a los usuarios que requieren que se apliquen restricciones de enrutamiento.

Para obtener más información sobre cómo crear directivas de enrutamiento de voz y asignarlas a los usuarios, vea [Administrar directivas de enrutamiento de voz en Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar el enrutamiento de Location-Based para sitios de red

Habilite el enrutamiento Location-Based para los sitios que necesitan aplicar restricciones de enrutamiento. Para ello, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Topología** de red **de ubicaciones** > , seleccione un sitio de red, haga clic en **Editar** y, a continuación, active el **enrutamiento basado en ubicación**.  

Para obtener más información, consulte [Administrar la topología de red](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar el enrutamiento de Location-Based para puertas de enlace

Habilite Location-Based Enrutamiento a puertas de enlace que redirien llamadas a puertas de enlace RTC que redirien llamadas a rtc y asocie el sitio de red donde se encuentra la puerta de enlace. 

1. En el panel de navegación izquierdo, vaya a **Enrutamiento directo** de **voz** >  y haga clic en la pestaña **SBCs**.

2. Seleccione el SBC y, a continuación, haga clic en **Editar**. 

3. En **Optimización de medios y enrutamiento basado en** ubicación, activa **Habilitar enrutamiento basado en ubicación**.

4. Especifique el id. de sitio de la puerta de enlace y, a continuación, establezca el modo de omisión.

5. Haga clic en **Guardar**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar el enrutamiento Location-Based para directivas de llamada

Para exigir Location-Based enrutamiento para usuarios específicos, configure la directiva de llamadas del usuario para evitar la omisión del pago RTC. Para ello, active la configuración **Evitar omisión de pago** en la directiva de llamada.

Para obtener más información, consulte [Directivas de llamadas en Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Con PowerShell

### <a name="enable-location-based-routing-for-users"></a>Habilitar el enrutamiento Location-Based para los usuarios

1. Para establecer los usos de RTC, use el cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) . Para varios usos, separe cada uso con una coma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    Por ejemplo:

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. Para crear una directiva de enrutamiento de voz que asocie al usuario con el uso de RTC adecuado, use el cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Al asignar usos de RTC a una directiva de enrutamiento de voz, asegúrese de realizar una de las siguientes acciones:

    - Use los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC local al sitio.

    - Use los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no son necesarias las restricciones de enrutamiento Location-Based.

    En el ejemplo siguiente se crean dos nuevas directivas de enrutamiento de voz y se les asignan usos de RTC. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    La tabla siguiente muestra las directivas de enrutamiento de voz definidas en este ejemplo. 
    
    |&nbsp;|Directiva de enrutamiento de voz 1|Directiva de enrutamiento de voz 2|
    |---------|---------|---------|
    |Id. de directiva de voz en línea   |Directiva de enrutamiento de voz en línea de Delhi   |Directiva de enrutamiento de voz en línea de Hyderabad    |
    |Usos de RTC en línea  |Larga distancia  |Larga distancia, local, interna  |

3. Para asociar directivas de enrutamiento de voz en línea a usuarios que requieren que se apliquen restricciones de enrutamiento, use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar el enrutamiento de Location-Based para sitios de red

1. Para habilitar el enrutamiento Location-Based y asociar las directivas de enrutamiento de voz a los sitios de red que necesitan aplicar restricciones de enrutamiento, use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) .

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Este ejemplo habilita el enrutamiento Location-Based para el sitio de Delhi y el sitio de Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    En la tabla siguiente se muestran los sitios habilitados para el enrutamiento de Location-Based en este ejemplo.

    |&nbsp;|Sitio 1 (Delhi)  |Sitio 2 (Hyderabad)  |
    |---------|---------|---------|
    |Nombre del sitio    |Sitio 1 (Delhi)    |Sitio 2 (Hyderabad)|
    |EnableLocationBasedRouting    |Verdadero    |True    |
    |Subredes     |Subred 1 (Delhi)     |Subred 2 (Hyderabad)     |


### <a name="enable-location-based-routing-for-gateways"></a>Habilitar el enrutamiento de Location-Based para puertas de enlace

1. Para crear una configuración de puerta de enlace para cada sitio de red o puerta de enlace, use el cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) . 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    Si hay varias puertas de enlace asociadas a un sistema (por ejemplo, puerta de enlace o PBX), modifique cada puerta de enlace para habilitar Location-Based Restricciones de enrutamiento. 

    En el ejemplo siguiente se crea una configuración de puerta de enlace para cada puerta de enlace. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Para obtener más información, consulte [Configurar enrutamiento directo](direct-routing-configure.md).
    
2. Para habilitar el enrutamiento Location-Based para las puertas de enlace que necesitan exigir restricciones de enrutamiento, use el cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) . 

    Habilite Location-Based Enrutamiento a puertas de enlace que redirien llamadas a puertas de enlace RTC que redirien llamadas a rtc y asocie el sitio de red donde se encuentra la puerta de enlace.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   En el ejemplo siguiente se habilita el enrutamiento de Location-Based para cada puerta de enlace asociada a puertas de enlace RTC en los sitios de Delhi y Hyderabad. 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    No habilite el enrutamiento de Location-Based para puertas de enlace que no enrute llamadas a la RTC. Sin embargo, todavía tiene que asociar la puerta de enlace al sitio de red donde se encuentra el sistema. Esto se debe a Location-Based Restricciones de enrutamiento deben aplicarse para las llamadas RTC que llegan a los puntos de conexión que están conectados a través de esta puerta de enlace. En este ejemplo, Location-Based enrutamiento no está habilitado para cada puerta de enlace asociada a sistemas PBX en los sitios de Delhi y Hyderabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar el enrutamiento Location-Based para directivas de llamada

Para exigir Location-Based enrutamiento para usuarios específicos, configure la directiva de voz de los usuarios para evitar la omisión del pago de PTSN. 

Para habilitar Location-Based enrutamiento impidiendo la omisión del pago RTC, use el cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) .


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

En este ejemplo, evitamos la omisión del pago RTC a las directivas de llamadas de Usuario1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)