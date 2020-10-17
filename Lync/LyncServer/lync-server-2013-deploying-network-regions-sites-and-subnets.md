---
title: 'Lync Server 2013: implementación de regiones de red, sitios y subredes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95d9f7e38e3169474aee33a3004b388c0b13f14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531153"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Implementar regiones de red, sitios y subredes en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

Una vez implementada la telefonía IP empresarial, debe configurar:

  - Regiones de red

  - Sitios de red

  - Subredes de red

<div>

## <a name="define-network-regions"></a>Definir regiones de red

Use el comando de Windows PowerShell de Lync Server, New-CsNetworkRegion o el panel de control de Lync Server para definir las regiones de red.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Para obtener más información, vea [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

Para este ejemplo, el siguiente comando de Windows PowerShell ilustra la región de red, región 1 (India), definida en este escenario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Definir sitios de red

Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite o el panel de control de Lync Server para definir sitios de red.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Para obtener más información, vea [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

Para este ejemplo, la siguiente tabla y el comando de Lync Server Windows PowerShell ilustran los sitios de red definidos en este escenario. En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.

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

Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSubnet o el panel de control de Lync Server para definir las subredes de red y asignarlas a los sitios de red.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Para obtener más información, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

En este ejemplo, los siguientes comandos de Windows PowerShell y tabla ilustran la asignación de subredes de red a los sitios de red, Delhi y Hyderabad, definidos en este escenario. En la tabla sólo se incluye la configuración específica de Location-Based enrutamiento para fines de ilustración.

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
<td><p>Mask</p></td>
<td><p>apartado</p></td>
<td><p>apartado</p></td>
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

## <a name="see-also"></a>Consulte también


[Configuración del enrutamiento de Location-Based en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

