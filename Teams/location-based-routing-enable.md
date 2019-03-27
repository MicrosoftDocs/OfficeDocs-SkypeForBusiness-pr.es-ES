---
title: Habilitar enrutamiento basado en la ubicación para el enrutamiento directo
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo habilitar el enrutamiento basados en ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68b239d00e67d942f80a259facb87c80ddf2a55
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886035"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar enrutamiento basado en la ubicación para el enrutamiento directo

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Antes de seguir los pasos descritos en este artículo, asegúrese de que ha leído [Plan Location-Based enrutamiento para el enrutamiento directo](location-based-routing-plan.md) y completado los pasos de [configuración de red para el enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md).

Este artículo describe cómo habilitar el enrutamiento basados en ubicación para el enrutamiento directo. Después de implementar el enrutamiento directo de teléfono del sistema y configurar regiones de red, sitios y subredes, estará listo habilitar el enrutamiento basado en la ubicación. Para completar los pasos descritos en este artículo, necesitará un poco familiarizado con los cmdlets de PowerShell. Para obtener más información, vea [Introducción a los equipos de PowerShell](teams-powershell-overview.md).

 Tiene que habilitar el enrutamiento basado en la ubicación para lo siguiente:
- Usuarios
- Sitios de red
- Configuraciones de puerta de enlace
- Llamar a las directivas

## <a name="enable-location-based-routing-for-users"></a>Habilitar el enrutamiento basado en la ubicación para los usuarios

1. Use el cmdlet [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer los usos de RTC. Para varios usos, separe cada uso con una coma.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Por ejemplo:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Use el cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz para asociar el usuario con los usos de RTC adecuados.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Al asignar los usos de RTC a una directiva de enrutamiento de voz, asegúrese de que se realice una de las siguientes opciones:
    - Use los usos de RTC asociados a las rutas de voz que usar una puerta de enlace de RTC local para el sitio
    - Use los usos de RTC asociados a las rutas de voz que usar una puerta de enlace de RTC que se encuentra en un área donde no son necesarias las restricciones de enrutamiento basado en la ubicación.

    En este ejemplo, creamos dos nuevas directivas enrutamiento de voz y asignar los usos de RTC a ellos. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    En la siguiente tabla muestra las directivas de enrutamiento de voz definidas en este ejemplo. 
    
    ||Directiva de enrutamiento 1 de voz|Directiva de enrutamiento 2 de voz|
    |---------|---------|---------|
    |Identificador de la directiva de voz en línea   |Directiva de enrutamiento de voz en línea de Delhi   |Directiva de enrutamiento de voz en línea de Hyderabad    |
    |Usos de RTC en línea  |Larga distancia  |Larga distancia, Local, interno  |

3. Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar las directivas de enrutamiento de voz en línea a los usuarios que requieren que se deben cumplir las restricciones de enrutamiento.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Habilitar el enrutamiento basado en la ubicación de sitios de red
1.  Use el cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar el enrutamiento basado en la ubicación y asociar las directivas de enrutamiento de voz a los sitios de red que se deben aplicar las restricciones de enrutamiento.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    En este ejemplo, se habilita enrutamiento basado en la ubicación del sitio de Delhi y el sitio de Hyderabad. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    En la siguiente tabla muestra los sitios habilitados para enrutamiento basado en la ubicación en este ejemplo.

    ||Sitio 1 (Delhi)  |Sitio 2 (Hyderabad)  |
    |---------|---------|---------|
|Nombre del sitio    |Sitio 1 (Delhi)    |Sitio 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Subredes     |Subred 1 (Delhi)     |Subred 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Habilitar el enrutamiento basado en la ubicación de las puertas de enlace
1. Use el cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada sitio de red o la puerta de enlace. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Si varias puertas de enlace están asociados con un sistema (por ejemplo, la puerta de enlace o PBX), modifique cada puerta de enlace para habilitar las restricciones de enrutamiento basado en la ubicación. 

    En este ejemplo, se crea una configuración de puerta de enlace para cada puerta de enlace. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Para obtener más información, vea [Configurar el enrutamiento directo](direct-routing-configure.md).
    
2. Use el cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar el enrutamiento basado en la ubicación de las puertas de enlace que se deben aplicar las restricciones de enrutamiento. 

    Habilitar el enrutamiento basado en la ubicación a puertas de enlace que enrutan las llamadas a las puertas de enlace de RTC que enrutan las llamadas a la RTC y asociación el sitio de red donde se encuentra la puerta de enlace.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    En este ejemplo, se habilita enrutamiento basado en la ubicación para cada puerta de enlace que está asociado a las puertas de enlace RTC en los sitios de Delhi y Hyderabad. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    No habilite el enrutamiento basado en la ubicación de las puertas de enlace que no enrutan las llamadas a la RTC. Sin embargo, aún debe asociar la puerta de enlace para el sitio de red donde se encuentra el sistema. Esto es debido a restricciones de enrutamiento basados en ubicación necesitan que se deben cumplir para alcanzar los extremos que están conectados a través de esta puerta de enlace de llamadas de RTC. En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada puerta de enlace que está asociado a sistemas PBX en los sitios de Delhi y Hyderabad.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Los extremos conectados a los sistemas que no enrutan las llamadas a la RTC (por ejemplo, un sistema PBX) tendrán restricciones similares como extremos de los usuarios de los equipos habilitados para enrutamiento basado en la ubicación. Esto significa que estos usuarios pueden realizar y recibir llamadas a y desde los usuarios de los equipos, independientemente de la ubicación del usuario. También puede realizar y recibir llamadas a y desde otros sistemas que no enrutan las llamadas a la red RTC (por ejemplo, un extremo conectado a un sistema PBX diferente) independientemente del sitio de red al que está asociado el sistema. Todas las llamadas entrantes, las llamadas salientes, transferencias de llamadas y el desvío de llamadas que implican los extremos de RTC estarán sujetas a las aplicaciones de enrutamiento basado en la ubicación. Estas llamadas deben usar sólo puertas de enlace RTC que se definen como locales para dichos sistemas. 

    En la siguiente tabla muestra la configuración de puerta de enlace de cuatro puertas de enlace en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |SUPR PstnGateway:Gateway 1-puerta de enlace    |    True     |   Sitio 1 (Delhi)      |
    |PstnGateway:Gateway 2 Hidráulico-puerta de enlace     |   True      |      Sitio 2 (Hyderabad)   |
    |PstnGateway:Gateway 3 SUPR-PBX    |    False     |     Sitio 1 (Delhi)    |
    |PstnGateway:Gateway 4 Hidráulico-PBX    |    False     |    Sitio 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar el enrutamiento basados en ubicación para llamar a las directivas

Para exigir la aplicación de enrutamiento basados en ubicación para usuarios específicos, el desvío de configurar la directiva de voz de los usuarios para evitar que el teléfono de pago PTSN. 

Use el cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el enrutamiento basado en ubicación al evitar el desvío de llamadas RTC.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
En este ejemplo, se evitar el desvío de pago de RTC del Usuario1 al llamar a las directivas de. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Temas relacionados
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Configuración de red de enrutamiento basado en la ubicación](location-based-routing-configure-network-settings.md)
- [Terminología de enrutamiento basado en la ubicación](location-based-routing-terminology.md)
