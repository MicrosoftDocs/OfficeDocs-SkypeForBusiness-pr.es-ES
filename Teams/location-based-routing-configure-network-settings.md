---
title: Configuración de red de enrutamiento basado en la ubicación
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a crear y configurar regiones, sitios y subredes de red para el enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570704"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configuración de red de enrutamiento basado en la ubicación

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Si aún no lo ha hecho, lea [planificar el enrutamiento basado en la ubicación para que el enrutamiento directo](location-based-routing-plan.md) Revise otros pasos que debe realizar antes de configurar la configuración de red para el enrutamiento basado en la ubicación.

En este artículo se describe cómo configurar las opciones de red para el enrutamiento basado en la ubicación. Después de implementar el enrutamiento directo de un sistema telefónico en su organización, los pasos siguientes son crear y configurar regiones de red, sitios de red y subredes de red. Para completar los pasos de este artículo, necesitará cierta familiaridad con los cmdlets de PowerShell. Para obtener más información, consulte [información general de Teams PowerShell](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Definir regiones de red
 Una región de red interconecta varias partes de una red en varias áreas geográficas. Use el cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) para definir regiones de red. Tenga en cuenta que el parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones, &lt;y el&gt; parámetro de identificador de sitio CentralSite es opcional. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

En este ejemplo, creamos una región de red denominada India. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Definir sitios de red

Use el cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sitios de red. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
En este ejemplo, creamos dos nuevos sitios de red, Delhi y Hyderabad, en la región de India. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
En la tabla siguiente se muestran los sitios de red definidos en este ejemplo. 

||Sitio 1 |Sitio 2 |
|---------|---------|---------|
|IDENTIFICADOR de sitio    |    Sitio 1 (Delhi)     |  Sitio 2 (Hyderabad)       |
|IDENTIFICADOR de región  |     Región 1 (India)    |   Región 1 (India)      |

## <a name="define-network-subnets"></a>Definir subredes de red

Use el cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir subredes de red y asociarlas a sitios de red. Cada subred interna solo se puede asociar con un sitio. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
En este ejemplo, creamos una asociación entre la subred 192.168.0.0 y el sitio de red de Delhi y entre la subred 2001:4898: E8:25:844e: 926f: 85ad: dd8e y el sitio de red de Hyderabad.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
En la tabla siguiente se muestran las subredes definidas en este ejemplo. 

||Sitio 1 |Sitio 2 |
|---------|---------|---------|
|IDENTIFICADOR de subred   |    192.168.0.0     |  2001:4898: E8:25:844e: 926f: 85ad: dd8e     |
|Sin  |     veinticuatro    |   120      |
|IDENTIFICADOR de sitio  | Sitio (Delhi) | Sitio 2 (Hyderabad) |

En el caso de varias subredes, puede importar un archivo CSV con una secuencia de comandos como la siguiente.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
En este ejemplo, el archivo CSV tiene un aspecto similar a este:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Definir subredes externas
Use el cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir subredes externas y asignarlas al inquilino. Puede definir un número ilimitado de subredes para un inquilino. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Por ejemplo:
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Pasos siguientes
Vaya a [Habilitar el enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-enable.md).

### <a name="related-topics"></a>Temas relacionados
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Terminología de enrutamiento basado en la ubicación](location-based-routing-terminology.md)
