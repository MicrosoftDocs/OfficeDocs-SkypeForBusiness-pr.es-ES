---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo habilitar Location-Based enrutamiento directo, incluida la habilitación para usuarios, sitios de red, configuraciones de puerta de enlace y directivas de llamadas.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dda26fafd48c56c11e2d6e085a1932a00307c64e96996bc30f22faaa80ed5639
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306392"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar enrutamiento basado en la ubicación para el enrutamiento directo

Antes de seguir los pasos de este artículo, asegúrese de que ha leído [Plan de enrutamiento Location-Based](location-based-routing-plan.md) para enrutamiento directo y ha completado los pasos de Configurar la configuración de red para Location-Based [enrutamiento.](location-based-routing-configure-network-settings.md)

En este artículo se describe cómo habilitar Location-Based enrutamiento directo. Después de implementar Sistema telefónico enrutamiento directo y configurar regiones de red, sitios y subredes, ya está listo para habilitar Location-Based enrutamiento. Para completar los pasos de este artículo, necesitará familiarizarse con los cmdlets de PowerShell. Para obtener más información, [vea Teams información general de PowerShell](teams-powershell-overview.md).

 Debe habilitar Location-Based enrutamiento para lo siguiente:
- Usuarios
- Sitios de red
- Configuraciones de puerta de enlace
- Directivas de llamada

Puede usar el Centro [de administración de Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerShel](#using-powershell)l para habilitar Location-Based enrutamiento.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based enrutamiento para usuarios

1. Cree una directiva de enrutamiento de voz y asigne usos RTC a la directiva. Al asignar usos de RTC a una directiva, asegúrese de realizar una de las siguientes acciones:

    - Use los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC local en el sitio.
    - Use los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan Location-Based restricciones de enrutamiento.
2. Asigne la directiva de enrutamiento de voz a los usuarios que requieran que se exijan restricciones de enrutamiento.

Para obtener más información sobre cómo crear directivas de enrutamiento de voz y asignarlas a los usuarios, vea Administrar directivas de enrutamiento de voz [en Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar Location-Based enrutamiento para sitios de red

Habilite Location-Based enrutamiento para los sitios que necesitan aplicar restricciones de enrutamiento. Para ello, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Topología de red de ubicaciones, seleccione un sitio de red, haga clic en Editar y, a continuación, active Enrutamiento basado en  >   **ubicación.**   

Para obtener más información, vea [Administrar la topología de red.](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar Location-Based enrutamiento de puertas de enlace

Habilite Location-Based enrutamiento a puertas de enlace que enrute llamadas a puertas de enlace RTC que enrute llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace. 

1. En el panel de navegación izquierdo, vaya a **Enrutamiento** directo  >  **de** voz y, a continuación, haga clic en la pestaña **SBC.**
2. Seleccione el SBC y, a continuación, haga clic **en Editar.** 
3. En **Enrutamiento basado en ubicación y optimización multimedia,** active Habilitar enrutamiento basado en **ubicación.**
4. Especifique el id. de sitio de la puerta de enlace y, después, establezca el modo de omisión.
5. Haga clic en **Guardar**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based enrutamiento para directivas de llamadas

Para exigir Location-Based enrutamiento para usuarios específicos, configure la directiva de llamadas del usuario para evitar la omisión de pago RTC. Para ello, active la configuración Evitar la omisión **de** pago en la directiva de llamadas.

Para obtener más información, vea [Directivas de llamadas en Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Con PowerShell

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based enrutamiento para usuarios

1. Use el cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer los usos de RTC. Para varios usos, separe cada uso con una coma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Por ejemplo:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Use el cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz para asociar al usuario con los usos RTC adecuados.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Al asignar usos rtc a una directiva de enrutamiento de voz, asegúrese de realizar una de las siguientes acciones:
    - Usar los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC local en el sitio
    - Use los usos rtc asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan Location-Based restricciones de enrutamiento.

    En este ejemplo, creamos dos nuevas directivas de enrutamiento de voz y les asignamos usos rtc. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    En la tabla siguiente se muestran las directivas de enrutamiento de voz definidas en este ejemplo. 
    
    ||Directiva de enrutamiento de voz 1|Directiva de enrutamiento de voz 2|
    |---------|---------|---------|
    |Id. de directiva de voz en línea   |Directiva de enrutamiento de voz en línea de Delhi   |Directiva de enrutamiento de voz en línea de Hyderabad    |
    |Usos de RTC en línea  |Larga distancia  |Distancia larga, Local, Interno  |

3. Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar directivas de enrutamiento de voz en línea a los usuarios que requieren que se exijan restricciones de enrutamiento.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar Location-Based enrutamiento para sitios de red

1.  Use el cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar Location-Based enrutamiento y asociar directivas de enrutamiento de voz a los sitios de red que necesitan aplicar restricciones de enrutamiento.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    En este ejemplo, habilitamos Location-Based enrutamiento para el sitio de Delhi y el sitio de Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    En la tabla siguiente se muestran los sitios habilitados para Location-Based enrutamiento en este ejemplo.

    ||Sitio 1 (Delhi)  |Sitio 2 (Hyderabad)  |
    |---------|---------|---------|
|Nombre del sitio    |Sitio 1 (Delhi)    |Sitio 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Subredes     |Subred 1 (Delhi)     |Subred 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar Location-Based enrutamiento de puertas de enlace

1. Use el cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada puerta de enlace o sitio de red. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Si varias puertas de enlace están asociadas a un sistema (por ejemplo, Puerta de enlace o PBX), modifique cada puerta de enlace para habilitar Location-Based de enrutamiento. 

    En este ejemplo, creamos una configuración de puerta de enlace para cada puerta de enlace. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md)
    
2. Use el cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar Location-Based enrutamiento para las puertas de enlace que necesitan aplicar restricciones de enrutamiento. 

    Habilite Location-Based enrutamiento a puertas de enlace que enrute llamadas a puertas de enlace RTC que enrute llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    En este ejemplo, habilitamos Location-Based enrutamiento para cada puerta de enlace asociada a puertas de enlace RTC en los sitios de Delhi y Hyderabad. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    No habilite el enrutamiento Location-Based las puertas de enlace que no enrutar llamadas a la RTC. Sin embargo, aún tiene que asociar la puerta de enlace al sitio de red donde se encuentra el sistema. Esto se debe a Location-Based restricciones de enrutamiento deben aplicarse para las llamadas RTC que lleguen a los puntos de conexión conectados a través de esta puerta de enlace. En este ejemplo, Location-Based enrutamiento no está habilitado para cada puerta de enlace asociada a sistemas PBX en los sitios de Delhi y Hyderabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based enrutamiento para directivas de llamadas

Para exigir Location-Based enrutamiento para usuarios específicos, configure la directiva de voz de los usuarios para evitar la omisión de pago de PTSN. 

Use el cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el Location-Based mediante la prevención de la omisión de pago RTC.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
En este ejemplo, evitamos la omisión de pago RTC a las directivas de llamadas de Usuario1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)