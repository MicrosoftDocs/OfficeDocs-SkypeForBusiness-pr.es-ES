---
title: "Dépl. des régions réseau, sites réseau et sous-réseaux dans Lync Server 2013"
TOCTitle: "Dépl. des régions réseau, sites réseau et sous-réseaux dans Lync Server 2013"
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994067(v=OCS.15)
ms:contentKeyID: 52061740
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de las regiones, sitios y subsitios de red en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Una vez implementado Telefonía IP empresarial, tiene que configurar:

  - Regiones de red

  - Sitios de red

  - Subredes de red

## Definir regiones de red

Utilice el comando del Windows PowerShell de Lync Server New-CsNetworkRegion, o el Panel de control de Lync Server, para definir las regiones de red.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Para obtener más información, consulte [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion).

En este ejemplo, el comando del Windows PowerShell que se muestra a continuación ilustra la definición de la región de red “región 1 (India)” en este escenario.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"


## Definir sitios de red

Utilice el comando del Windows PowerShell de Lync Server New-CsNetworkSite, o el Panel de control de Lync Server, para definir los sitios de red.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Para obtener más información, consulte [New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite).

En este ejemplo, la siguiente tabla y el comando Lync ServerWindows PowerShell representan la definición de sitios de red de este escenario. Para facilitar la comprensión, la tabla solo incluye las opciones de configuración específicas del enrutamiento basado en ubicación.

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
<th>Sitio 1 (Delhi)</th>
<th>Sitio 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Identificador de sitio</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>Identificador de región</p></td>
<td><p>Región 1 (India)</p></td>
<td><p>Región 1 (India)</p></td>
</tr>
</tbody>
</table>



## Definir subredes de red

Utilice el comando del Windows PowerShell de Lync Server New-CsNetworkSubnet, o el Panel de control de Lync Server, para definir las subredes de red y asignarlas a los sitios de red.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Para obtener más información, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

En este ejemplo, la siguiente tabla y los comandos del Windows PowerShell representan la asignación de subredes de red a los sitios de red definidos en este escenario, Delhi y Hyderabad. Para facilitar la comprensión, la tabla solo incluye las opciones de configuración específicas del enrutamiento basado en ubicación.

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
<th>Sitio 1 (Delhi)</th>
<th>Sitio 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Identificador de subred</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Máscara</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Identificador de sitio</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Vea también

#### Otros recursos

[Configurar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

