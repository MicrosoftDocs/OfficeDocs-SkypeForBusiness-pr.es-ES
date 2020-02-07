---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo habilitar el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 734a2354e81dc88430e8f880c46b0f97862158b5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836560"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar enrutamiento basado en la ubicación para el enrutamiento directo

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Antes de seguir los pasos de este artículo, asegúrese de que ha leído [planear el enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md) y completado los pasos de [configurar la configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).

En este artículo se describe cómo habilitar el enrutamiento basado en la ubicación para el enrutamiento directo. Después de implementar el enrutamiento directo de un sistema telefónico y configurar regiones, sitios y subredes de la red, está listo para habilitar el enrutamiento basado en la ubicación. Para completar los pasos de este artículo, necesitará cierta familiaridad con los cmdlets de PowerShell. Para obtener más información, consulte [información general de Teams PowerShell](teams-powershell-overview.md).

 Debe habilitar el enrutamiento basado en la ubicación para lo siguiente:
- Usuarios
- Sitios de red
- Configuraciones de puerta de enlace
- Directivas de llamadas

## <a name="enable-location-based-routing-for-users"></a>Habilitar el enrutamiento basado en la ubicación para los usuarios

1. Use el cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer usos de RTC. Para varios usos, separe cada uso con una coma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Por ejemplo:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Use el cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz y asociar al usuario los usos de RTC apropiados.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Cuando asigne usos de RTC a una directiva de enrutamiento de voz, asegúrese de realizar una de las siguientes acciones:
    - Usar usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC local para el sitio
    - Use usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC ubicada en una región donde no se necesitan restricciones de enrutamiento basadas en la ubicación.

    En este ejemplo, creamos dos nuevas directivas de enrutamiento de voz y se les asignan usos de RTC. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    En la tabla siguiente se muestran las directivas de enrutamiento de voz definidas en este ejemplo. 
    
    ||Directiva de enrutamiento de voz 1|Directiva de enrutamiento de voz 2|
    |---------|---------|---------|
    |IDENTIFICADOR de directiva de voz en línea   |Directiva de enrutamiento de voz en línea de Delhi   |Directiva de enrutamiento de voz en línea de Hyderabad    |
    |Usos de RTC en línea  |Larga distancia  |Larga distancia, local, interna  |

3. Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar directivas de enrutamiento de voz en línea a los usuarios que necesiten exigir restricciones de enrutamiento.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Habilitar el enrutamiento basado en la ubicación de los sitios de red
1.  Use el cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar el enrutamiento basado en la ubicación y para asociar directivas de enrutamiento de voz a los sitios de red que necesitan exigir restricciones de enrutamiento.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    En este ejemplo, habilitamos el enrutamiento basado en la ubicación para el sitio de Delhi y el sitio de Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    En la tabla siguiente se muestran los sitios habilitados para el enrutamiento basado en la ubicación en este ejemplo.

    ||Sitio 1 (Delhi)  |Sitio 2 (Hyderabad)  |
    |---------|---------|---------|
|Nombre del sitio    |Sitio 1 (Delhi)    |Sitio 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Subredes     |Subred 1 (Delhi)     |Subred 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Habilitar enrutamiento basado en la ubicación para puertas de enlace
1. Use el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada puerta de enlace o sitio de red. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Si hay varias puertas de enlace asociadas a un sistema (por ejemplo, puerta de enlace o PBX), modifique cada puerta de enlace para habilitar las restricciones de enrutamiento basadas en la ubicación. 

    En este ejemplo, creamos una configuración de puerta de enlace para cada puerta de enlace. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md).
    
2. Use el cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar el enrutamiento basado en la ubicación para las puertas de enlace que necesitan exigir restricciones de enrutamiento. 

    Habilite el enrutamiento basado en la ubicación a las puertas de enlace que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    En este ejemplo, habilitamos el enrutamiento basado en la ubicación para cada puerta de enlace que está asociada a las puertas de enlace RTC en los sitios de Delhi y Hyderabad. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    No habilite el enrutamiento basado en la ubicación para puertas de enlace que no enruten llamadas a la RTC. Sin embargo, aún tiene que asociar la puerta de enlace al sitio de red en el que se encuentra el sistema. Esto se debe a que las restricciones de enrutamiento basadas en la ubicación deben exigirse para que las llamadas RTC lleguen a los puntos de conexión que se conectan a través de esta puerta de enlace. En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada puerta de enlace que está asociada a sistemas PBX de la Delhi y los sitios de Hyderabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Los puntos de conexión conectados a los sistemas que no enruten las llamadas a la RTC (por ejemplo, una PBX) tendrán restricciones similares a las de los usuarios de Teams habilitados para el enrutamiento basado en la ubicación. Esto significa que estos usuarios pueden realizar y recibir llamadas a usuarios de Teams y desde ellos, independientemente de la ubicación del usuario. También pueden realizar y recibir llamadas a y desde otros sistemas que no enruten las llamadas a la red PSTN (por ejemplo, un extremo conectado a otro sistema PBX), independientemente del sitio de red al que esté asociado el sistema. Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas que implican puntos de conexión RTC estarán sujetas a las fuerzas de enrutamiento basadas en la ubicación. Estas llamadas deben usar solo puertas de enlace RTC que estén definidas como locales para esos sistemas. 

    En la tabla siguiente se muestra la configuración de puerta de enlace de cuatro puertas de enlace en dos sitios de red diferentes: dos conectadas a puertas de enlace RTC y dos conectadas a sistemas PBX. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway: puerta de enlace 1 DEL-GW    |    Verdadero     |   Sitio 1 (Delhi)      |
    |PstnGateway: puerta de enlace 2 HYD-GW     |   Verdadero      |      Sitio 2 (Hyderabad)   |
    |PstnGateway: puerta de enlace 3 DEL-PBX    |    Falso     |     Sitio 1 (Delhi)    |
    |PstnGateway: puerta de enlace 4 HYD-PBX    |    Falso     |    Sitio 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar el enrutamiento basado en la ubicación para las directivas de llamadas

Para aplicar el enrutamiento basado en la ubicación para usuarios específicos, configure la Directiva de voz de los usuarios para evitar la omisión de RTC de pago. 

Use el cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el enrutamiento basado en la ubicación evitando la omisión de llamadas RTC.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
En este ejemplo, evitamos la omisión de llamadas de RTC a directivas de llamadas de Usuario1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red de las características de voz en la nube en Teams](cloud-voice-network-settings.md)
