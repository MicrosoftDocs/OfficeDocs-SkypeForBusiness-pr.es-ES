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
description: Obtenga información sobre cómo habilitar Location-Based para enrutamiento directo, lo que incluye habilitarlo para usuarios, sitios de red, configuraciones de puerta de enlace y directivas de llamadas.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822920"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar enrutamiento basado en la ubicación para el enrutamiento directo

Antes de seguir los pasos de este artículo, asegúrese de que ha leído [Plan Location-Based](location-based-routing-plan.md) Enrutamiento directo y haya completado los pasos de Configurar la configuración de red para Location-Based [enrutamiento.](location-based-routing-configure-network-settings.md)

En este artículo se describe cómo habilitar el enrutamiento Location-Based para enrutamiento directo. Después de implementar el enrutamiento directo de sistema telefónico y configurar las regiones, los sitios y las subredes de red, ya puede habilitar el enrutamiento Location-Based teléfono. Para completar los pasos de este artículo, necesitará estar familiarizado con los cmdlets de PowerShell. Para obtener más información, consulte [Información general de PowerShell de Teams.](teams-powershell-overview.md)

 Debe habilitar el enrutamiento de Location-Based para lo siguiente:
- Usuarios
- Sitios de red
- Configuraciones de puerta de enlace
- Directivas de llamada

Puede usar el Centro [de administración de Microsoft Team](#using-the-microsoft-teams-admin-center) o [PowerSadministr para](#using-powershell)habilitar el enrutamiento Location-Based equipo.

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based de acceso directo para los usuarios

1. Cree una directiva de enrutamiento de voz y asigne usos de RTC a la directiva. Al asignar usos de RTC a una directiva, asegúrese de realizar una de las siguientes acciones:

    - Use los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC local en el sitio.
    - Use los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región en la que Location-Based no son necesarias restricciones de enrutamiento.
2. Asigne la directiva de enrutamiento de voz a los usuarios que requieran que se apliquen restricciones de enrutamiento.

Para obtener más información sobre cómo crear directivas de enrutamiento de voz y asignarlas a los usuarios, vea Administrar directivas de enrutamiento de [voz en Microsoft Teams.](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar el Location-Based de acceso directo para sitios de red

Habilite Location-Based para los sitios que necesitan aplicar restricciones de enrutamiento. Para ello, en el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a la topología de red Ubicaciones, seleccione un sitio de red, haga clic en Editar y active el enrutamiento basado en  >   **ubicaciones.**   

Para obtener más información, [vea Administrar la topología de red.](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar el Location-Based de acceso directo para las puertas de enlace

Habilite Location-Based a puertas de enlace que enrutar llamadas a puertas de enlace RTC que enrutar llamadas a la RTC y asociar el sitio de red donde se encuentra la puerta de enlace. 

1. En el panel de navegación izquierdo, vaya a **Enrutamiento** directo de voz y, a continuación, haga clic  >  en la pestaña **SBC.**
2. Seleccione la SBC y, a continuación, haga clic **en Editar.** 
3. En **Optimización de medios y enrutamiento basados** en la **ubicación, active el enrutamiento basado en la ubicación.**
4. Especifique el id. de sitio de la puerta de enlace y establezca el modo de omisión.
5. Haga clic en **Guardar**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based de llamadas

Para exigir Location-Based de llamadas para usuarios específicos, configure la directiva de llamadas del usuario para evitar la omisión de pago RTC. Para ello, active la configuración Evitar omisión de **pago** en la directiva de llamadas.

Para obtener más información, consulte [Directivas de llamadas en Teams.](teams-calling-policy.md)

## <a name="using-powershell"></a>Con PowerShell

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based de acceso directo para los usuarios

1. Use el [cmdlet Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para establecer los usos de RTC. Para varios usos, se separa cada uso con una coma.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Por ejemplo:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Use el [cmdlet New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para crear una directiva de enrutamiento de voz para asociar al usuario a los usos de RTC adecuados.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Al asignar usos de RTC a una directiva de enrutamiento de voz, asegúrese de realizar una de las siguientes acciones:
    - Usar los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC local en el sitio
    - Use los usos de RTC asociados a las rutas de voz que usan una puerta de enlace RTC ubicada en una región en la que Location-Based no son necesarias restricciones de enrutamiento.

    En este ejemplo, creamos dos nuevas directivas de enrutamiento de voz y les asignamos usos de RTC. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    En la tabla siguiente se muestran las directivas de enrutamiento de voz definidas en este ejemplo. 
    
    ||Directiva de enrutamiento de voz 1|Directiva de enrutamiento de voz 2|
    |---------|---------|---------|
    |Id. de directiva de voz en línea   |Directiva de enrutamiento de voz en línea de Protocol   |Directiva de enrutamiento de voz en línea de Rgpd    |
    |Usos de RTC en línea  |Long Distance  |Larga distancia, local, interno  |

3. Use el cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para asociar las directivas de enrutamiento de voz en línea a los usuarios que requieran que se apliquen restricciones de enrutamiento.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar el Location-Based de acceso directo para sitios de red

1.  Use el [cmdlet Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar el enrutamiento de Location-Based y asociar las directivas de enrutamiento de voz a los sitios de red que necesitan aplicar restricciones de enrutamiento.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    En este ejemplo, se habilita el enrutamiento Location-Based para el sitio deVer y el sitio deAbad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    En la tabla siguiente se muestran los sitios habilitados para el Location-Based en este ejemplo.

    ||Sitio 1 (Cca)  |Sitio 2 (Jordaniarabad)  |
    |---------|---------|---------|
|Nombre del sitio    |Sitio 1 (Cca)    |Sitio 2 (Jordaniarabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |Subredes     |Subred 1 (Québa)     |Subred 2 (Jordaniarabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar el Location-Based de acceso directo para las puertas de enlace

1. Use el [cmdlet New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para crear una configuración de puerta de enlace para cada puerta de enlace o sitio de red. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Si hay varias puertas de enlace asociadas a un sistema (por ejemplo, puerta de enlace o PBX), modifique cada puerta de enlace para habilitar Location-Based de enrutamiento. 

    En este ejemplo, se crea una configuración de puerta de enlace para cada puerta de enlace. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Para obtener más información, vea [Configurar enrutamiento directo.](direct-routing-configure.md)
    
2. Use el cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar el enrutamiento de Location-Based para las puertas de enlace que necesitan aplicar restricciones de enrutamiento. 

    Habilite Location-Based a puertas de enlace que enrutar llamadas a puertas de enlace RTC que enrutar llamadas a la RTC y asociar el sitio de red donde se encuentra la puerta de enlace.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    En este ejemplo, habilitamos el enrutamiento Location-Based para cada puerta de enlace asociada a puertas de enlace RTC en los sitios de Boston y Rtc. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    No habilite el enrutamiento Location-Based las puertas de enlace que no enrutar llamadas a LA RTC. Sin embargo, aún debe asociar la puerta de enlace al sitio de red donde se encuentra el sistema. Esto se debe a Location-Based es necesario aplicar restricciones de enrutamiento para las llamadas RTC que lleguen a los puntos de conexión que están conectados a través de esta puerta de enlace. En este ejemplo, Location-Based enrutamiento no está habilitado para todas las puertas de enlace asociadas a sistemas PBX en los sitios deControl y Rtc.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based de llamadas

Para aplicar el Location-Based de acceso directo para usuarios específicos, configure la directiva de voz de los usuarios para evitar la omisión de pago por ptSN. 

Use el [cmdlet Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar el enrutamiento Location-Based rtc al impedir la omisión de pago RTC.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
En este ejemplo, evitamos la omisión de pago RTC para las directivas de llamadas de Usuario1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red para las características de voz en la nube en Teams](cloud-voice-network-settings.md)
