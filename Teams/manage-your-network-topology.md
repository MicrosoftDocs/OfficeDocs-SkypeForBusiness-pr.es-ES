---
title: Administrar la topología de red para las características de voz en la nube en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo configurar la configuración de red para las características de voz en la nube en Microsoft Teams.
ms.openlocfilehash: c77f1e6d31953ce529bff1fab6aa16e1d889e29f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101066"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Administrar la topología de red para las características de voz en la nube en Microsoft Teams

Si su organización [](location-based-routing-plan.md) implementa enrutamiento basado en la ubicación para enrutamiento directo o llamadas de emergencia dinámicas, [](configure-dynamic-emergency-calling.md)debe configurar la configuración de red para usarla con estas características de voz en la nube en Microsoft Teams. La configuración de red se usa para determinar la ubicación de un cliente de Teams e incluye regiones de red, sitios de red, subredes y direcciones IP de confianza. En función de la característica y la capacidad de voz en la nube que implemente, puede configurar algunas o todas estas opciones de configuración. Para obtener más información sobre estos términos, vea [Configuración de red para las características de voz en la nube.](cloud-voice-network-settings.md)

Puede configurar la configuración de red en la **página Topología de** red del Centro de administración de Microsoft Teams o mediante Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Configurar la configuración de red en el Centro de administración de Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Defina regiones de red, sitios de red y subredes en la pestaña Sitios **de** red de la **página Topología de** red. Aquí puede crear o modificar un sitio de red, asociar un sitio a una región de red, asociar una subred al sitio, activar enrutamiento basado en ubicación y asignar directivas de emergencia al sitio. También puede agregar regiones de red que se pueden usar globalmente para todos los sitios.

#### <a name="add-and-configure-a-network-site"></a>Agregar y configurar un sitio de red

1. En la navegación izquierda del Centro de administración de Microsoft Teams, vaya **a** Topología de red de ubicaciones y, a continuación, haga clic en la  >  pestaña Sitios **de** red.
2. Haga **clic en** Agregar y, a continuación, escriba un nombre y una descripción para el sitio.

    ![Captura de pantalla de la página Agregar sitio de red](media/manage-network-topology-add-site.png)

3. Para asociar el sitio a una región de red, haga  clic en Agregar región de **red,** seleccione una región existente o haga clic en Agregar para agregar una región y, a continuación, haga clic en **Vincular.**  
4. Para habilitar Location-Based enrutamiento para el sitio, active **Enrutamiento basado en ubicación.**
5. Para asignar directivas de servicios de emergencia al sitio, realice una o ambas acciones:

    - Si su organización usa planes de llamadas o enrutamiento directo del sistema telefónico implementado, en **Directiva** de llamadas de emergencia, seleccione la directiva que desee.
    - Si su organización implementó enrutamiento directo del sistema telefónico, en Directiva de enrutamiento de **llamadas de emergencia,** seleccione la directiva que desee.

6. Para asociar una subred al sitio, en **Subredes,** haga clic **en Agregar subredes.** Especifique la versión IP, la dirección IP, el rango de red, agregue una descripción y, a continuación, haga clic en **Aplicar.** Cada subred debe estar asociada a un sitio específico.
7. Haga clic en **Guardar**.

#### <a name="modify-a-network-site"></a>Modificar un sitio de red

1. En la navegación izquierda del Centro de administración de Microsoft Teams, vaya **a** Topología de red de ubicaciones y, a continuación, haga clic en la  >  pestaña Sitios **de** red.
2. Seleccione el sitio haciendo clic a la izquierda del nombre del sitio y, a continuación, haga clic en **Editar.**
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="manage-external-trusted-ip-addresses"></a>Administrar direcciones IP de confianza externa

Puede administrar direcciones IP de confianza externa en la pestaña **Ip de** confianza en la página Topología **de** red del Centro de administración de Microsoft Teams. Puede agregar un número ilimitado de direcciones IP de confianza externa.

#### <a name="add-a-trusted-ip-address"></a>Agregar una dirección IP de confianza

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Topología de red de ubicaciones y, a continuación, haga clic en  >  la pestaña **Ip de** confianza.
2. Haga clic en **Nuevo**.
3. En el **panel Agregar dirección IP de** confianza, especifique la versión IP, la dirección IP, el rango de red, agregue una descripción y, a continuación, haga clic en **Aplicar.**

    ![Captura de pantalla del panel Agregar dirección IP de confianza](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Editar una dirección IP de confianza

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Topología de red de ubicaciones y, a continuación, haga clic en  >  la pestaña **Ip de** confianza.
2. Seleccione la dirección IP haciendo clic a la izquierda y, a continuación, haga clic en **Editar.**
3. En el **panel Editar dirección IP de** confianza, realice los cambios que desee y, a continuación, haga clic en **Aplicar.**

## <a name="configure-network-settings-using-powershell"></a>Configurar la configuración de red con PowerShell

Para completar los pasos de esta sección, necesitará familiarizarse con los cmdlets de PowerShell. Para obtener más información, vea [Información general de PowerShell de Teams.](teams-powershell-overview.md)

### <a name="define-network-regions"></a>Definir regiones de red

 Use el cmdlet [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) para definir regiones de red. Tenga en cuenta que el parámetro Id. de región es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones y el parámetro Id. de sitio de Sitio central &lt; &gt; es opcional.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

En este ejemplo, creamos una región de red denominada India.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Vea también [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Definir sitios de red

Use el cmdlet [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sitios de red. Cada sitio de red debe estar asociado a una región de red.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

En este ejemplo, creamos dos nuevos sitios de red, Delhi y Hyderabad, en la región india.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

En la tabla siguiente se muestran los sitios de red definidos en este ejemplo.

||Sitio 1 |Sitio 2 |
|---------|---------|---------|
|Id. de sitio    |    Sitio 1 (Delhi)     |  Sitio 2 (Hyderabad)       |
|Id. de región  |     Región 1 (India)    |   Región 1 (India)      |

Vea también [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Definir subredes de red

Use el cmdlet [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir subredes de red y asociarlas a sitios de red. Cada subred de red solo se puede asociar a un sitio.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

En este ejemplo, creamos una asociación entre la subred 192.168.0.0 y el sitio de red de Delhi y entre la subred 2001:4898:e8:25:844e:926f:85ad:dd8e y el sitio de red de Hyderabad.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

En la tabla siguiente se muestran las subredes definidas en este ejemplo.

||Sitio 1 |Sitio 2 |
|---------|---------|---------|
|Id. de subred   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Máscara  |     24    |   120      |
|Id. de sitio  | Sitio (Delhi) | Sitio 2 (Hyderabad) |

Para varias subredes, puede importar un archivo CSV mediante un script como el siguiente.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

En este ejemplo, el archivo CSV tiene un aspecto similar a este:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


Vea también [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definir subredes externas (direcciones IP de confianza externas)

Use el cmdlet [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir subredes externas y asignarlas al inquilino. Puede definir un número ilimitado de subredes externas para un inquilino.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Por ejemplo:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Vea también [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red para características de voz en la nube en Teams](cloud-voice-network-settings.md)
