---
title: Configuración de red de enrutamiento basado en la ubicación
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y configurar regiones de red, sitios y subredes para enrutamiento basado en la ubicación para el enrutamiento directo.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60ed4b1c69f2b6495e21fe28653b19ca905dfc6c
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353445"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configuración de red de enrutamiento basado en la ubicación

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Si ya lo ha hecho, lea [Plan Location-Based enrutamiento para el enrutamiento directo](location-based-routing-plan.md) para revisar otros pasos debe tomar antes de implementar la configuración de red para el enrutamiento basado en la ubicación.

Este artículo describe cómo configurar las opciones de red para el enrutamiento basado en la ubicación. Después de implementar el enrutamiento directo teléfono del sistema en la organización, son los siguientes pasos crear y configurar regiones de red, sitios de red y subredes de la red. Para completar los pasos descritos en este artículo, necesitará un poco familiarizado con los cmdlets de PowerShell. Para obtener más información, vea [Introducción a los equipos de PowerShell](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Definir regiones de red
 Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas. Usar el ``New-CsTenantNetworkRegion`` cmdlet de PowerShell para definir regiones de red. Tenga en cuenta que el ``RegionID`` parámetro es un nombre lógico que representa la región geográfica de la región y no tiene dependencias ni las restricciones y el ``CentralSite <site ID>`` parámetro es opcional. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

En este ejemplo, se crea una región de red denominada India. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Definir sitios de red

Usar el ``New-CsTenantNetworkSite`` cmdlet de PowerShell para definir sitios de red. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
En este ejemplo, creamos dos nuevos sitios de red, Delhi y Hyderabad, en la región de India. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
En la siguiente tabla muestra los sitios de red definidos en este ejemplo. 

||Sitio 1 |Sitio 2 |
|---------|---------|---------|
|Identificador de sitio    |    Sitio 1 (Delhi)     |  Sitio 2 (Hyderabad)       |
|Identificador de región  |     Región 1 (India)    |   Región 1 (India)      |

## <a name="define-network-subnets"></a>Definir subredes de red

Usar el ``New-CsTenantNetworkSubnet`` cmdlet para definir subredes de red y asociarlos a sitios de red. Sólo se puede asociar con un sitio cada subred interna. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
En este ejemplo, se crea una asociación entre la subred 192.168.0.0 y el sitio de red de Delhi y entre la subred 192.168.1.0 y el sitio de red de Hyderabad.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
En la siguiente tabla muestra las subredes definidas en este ejemplo. 

||Sitio 1 |Sitio 2 |
|---------|---------|---------|
|Identificador de subred   |    192.168.0.0     |  192.168.1.0     |
|Máscara  |     24    |   24      |
|Identificador de sitio  | Sitio (Delhi) | Sitio 2 (Hyderabad) |

Para varias subredes, puede importar un archivo CSV mediante el uso de una secuencia de comandos como la siguiente.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
En este ejemplo, el archivo CSV tiene el aspecto similar al siguiente:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Definir subredes externas
Usar el ``New-CsTenantTrustedIPAddress`` cmdlet para definir subredes externas y asignarlas a los inquilinos. Puede definir un número ilimitado de subredes de un inquilino. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Por ejemplo:
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Pasos siguientes
Vaya a [Habilitar el enrutamiento basado en ubicación para el enrutamiento directo](location-based-routing-enable.md).

### <a name="related-topics"></a>Temas relacionados
- [Planear enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md)
- [Terminología de enrutamiento basado en la ubicación](location-based-routing-terminology.md)
