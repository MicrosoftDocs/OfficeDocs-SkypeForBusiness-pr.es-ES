---
title: Administrar la topología de red para las características de voz en la nube en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo configurar las opciones de red para las características de voz en la nube en Microsoft Teams.
ms.openlocfilehash: 03eaeac1bce07cffa7dc000f964f080361a37d40
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539630"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Administrar la topología de red para las características de voz en la nube en Microsoft Teams

Si su organización está implementando [enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md) o las [llamadas de emergencia dinámicas](configure-dynamic-emergency-calling.md), debe configurar las opciones de red para usarlas con estas características de voz de nube en Microsoft Teams. La configuración de red se usa para determinar la ubicación de un cliente de equipo e incluir regiones de red, sitios de red, subredes y direcciones IP de confianza. En función de la característica de voz de nube y de la capacidad de implementación, debe configurar algunas o todas estas opciones. Para obtener más información sobre estos términos, consulte [configuración de red para características de voz en la nube](cloud-voice-network-settings.md).

La configuración de red se establece en la página **topología de red** del centro de administración de Microsoft Teams o mediante Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Configurar las opciones de red en el centro de administración de Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Defina regiones de red, sitios de red y subredes en la ficha **sitios de red** de la página topología de **red** . Aquí puede crear o modificar un sitio de red, asociar un sitio con una región de red, asociar una subred al sitio, activar el enrutamiento basado en la ubicación y asignar directivas de emergencia al sitio. También puede Agregar regiones de red que se pueden usar globalmente para todos los sitios.

#### <a name="add-and-configure-a-network-site"></a>Agregar y configurar un sitio de red

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **sitios de red** .
2. Haga clic en **Agregar**y, a continuación, escriba un nombre y una descripción para el sitio.

    ![Captura de pantalla de la página Agregar sitio de red](media/manage-network-topology-add-site.png)

3. Para asociar el sitio con una región de red, haga clic en **Agregar región de red**, seleccione una región existente o haga clic en **Agregar** para agregar una región y, a continuación, haga clic en **vincular**.  
4. Para habilitar el enrutamiento basado en la ubicación del sitio, active el **enrutamiento basado**en la ubicación.
5. Para asignar directivas de servicios de emergencia al sitio, realice una de las siguientes acciones o ambas:

    - Si su organización usa planes de llamadas o enrutamiento directo de sistema telefónico implementado, en **Directiva de llamadas de emergencia**, seleccione la Directiva que desee.
    - Si su organización ha implementado el enrutamiento de un sistema telefónico directo, en **Directiva de enrutamiento de llamadas de emergencia**, seleccione la Directiva que quiera.

6. Para asociar una subred al sitio, en **subredes**, haga clic en **Agregar subredes**. Especifique la versión IP, la dirección IP, el intervalo de red, agregue una descripción y, a continuación, haga clic en **aplicar**. Cada subred debe estar asociada a un sitio específico.
7. Haga clic en **Guardar **.

#### <a name="modify-a-network-site"></a>Modificar un sitio de red

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **sitios de red** .
2. Seleccione el sitio haciendo clic a la izquierda del nombre del sitio y, a continuación, haga clic en **Editar**.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="manage-external-trusted-ip-addresses"></a>Administrar direcciones IP de confianza externas

Las direcciones IP de confianza externas se administran en la ficha **IP fiables** de la página **topología de red** del centro de administración de Microsoft Teams. Puedes añadir un número ilimitado de direcciones IP de confianza externas.

#### <a name="add-a-trusted-ip-address"></a>Agregar una dirección IP fiable

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **IP fiables** .
2. Haga clic en **Nuevo**.
3. En el panel **Agregar una dirección IP de confianza** , especifique la versión IP, la dirección IP, el intervalo de red, agregue una descripción y, a continuación, haga clic en **aplicar**.

    ![Captura de pantalla del panel agregar dirección IP fiable](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Modificar una dirección IP fiable

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **ubicaciones**de  >  **red**y, a continuación, haga clic en la pestaña **IP fiables** .
2. Seleccione la dirección IP haciendo clic a la izquierda y, a continuación, haga clic en **Editar**.
3. En el panel **Editar direcciones IP fiables** , realice los cambios que desee y, a continuación, haga clic en **aplicar**.

## <a name="configure-network-settings-using-powershell"></a>Configurar las opciones de red con PowerShell

Para completar los pasos de esta sección, necesitará cierta familiaridad con los cmdlets de PowerShell. Para obtener más información, consulte [información general de Teams PowerShell](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Definir regiones de red

 Use el cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) para definir regiones de red. Tenga en cuenta que el parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones, y el &lt; parámetro de identificador de sitio CentralSite &gt; es opcional.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

En este ejemplo, creamos una región de red denominada India.
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Consulte también [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Definir sitios de red

Use el cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sitios de red. Cada sitio de red debe estar asociado a una región de red.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

En este ejemplo, creamos dos nuevos sitios de red, Delhi y Hyderabad, en la región de India.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

En la tabla siguiente se muestran los sitios de red definidos en este ejemplo.

||Sitio 1 |Sitio 2 |
|---------|---------|---------|
|IDENTIFICADOR de sitio    |    Sitio 1 (Delhi)     |  Sitio 2 (Hyderabad)       |
|IDENTIFICADOR de región  |     Región 1 (India)    |   Región 1 (India)      |

Consulte también [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Definir subredes de red

Use el cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir subredes de red y asociarlas a sitios de red. Cada subred de red solo se puede asociar con un sitio.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

En este ejemplo, creamos una asociación entre la subred 192.168.0.0 y el sitio de red de Delhi y entre la subred 2001:4898: E8:25:844e: 926f: 85ad: dd8e y el sitio de red de Hyderabad.

```PowerShell
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

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

En este ejemplo, el archivo CSV tiene un aspecto similar a este:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

Consulte también [set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Definir subredes externas (direcciones IP externas de confianza)

Use el cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir subredes externas y asignarlas al inquilino. Puede definir un número ilimitado de subredes externas para un inquilino.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Por ejemplo:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Consulte también [set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Temas relacionados

- [Configuración de red de las características de voz en la nube en Teams](cloud-voice-network-settings.md)
