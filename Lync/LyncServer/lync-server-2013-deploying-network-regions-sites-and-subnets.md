---
title: 'Lync Server 2013: implementar regiones, sitios y subredes de la red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e75c18a582be046755a54656e9f367edabdda3e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Implementar regiones, sitios y subredes de la red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

Una vez implementada la voz de la empresa, debe configurar:

  - Regiones de red

  - Sitios de red

  - Subredes de red

<div>

## <a name="define-network-regions"></a>Definir regiones de red

Use el comando de Windows PowerShell de Lync Server, New-CsNetworkRegion o panel de control de Lync Server para definir las regiones de red.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Para obtener más información, vea [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

En este ejemplo, el siguiente comando de Windows PowerShell muestra la región de red, región 1 (India), definida en este escenario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Definir sitios de red

Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite o el panel de control de Lync Server para definir sitios de red.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Para obtener más información, vea [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

En este ejemplo, la siguiente tabla y el comando de Windows PowerShell de Lync Server muestran los sitios de red definidos en este escenario. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Sitio 1 (Delhi)</th>
<th>Sitio 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IDENTIFICADOR de sitio</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>IDENTIFICADOR de región</p></td>
<td><p>Región 1 (India)</p></td>
<td><p>Región 1 (India)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>Definir subredes de red

Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSubnet o el panel de control de Lync Server para definir subredes de red y asignarlas a sitios de red.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Para obtener más información, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

En este ejemplo, los siguientes comandos de tabla y Windows PowerShell ilustran la asignación de subredes de red a los sitios de red, Delhi y Hyderabad, definidas en este escenario. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Sitio 1 (Delhi)</th>
<th>Sitio 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IDENTIFICADOR de subred</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Sin</p></td>
<td><p>veinticuatro</p></td>
<td><p>veinticuatro</p></td>
</tr>
<tr class="odd">
<td><p>IDENTIFICADOR de sitio</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

