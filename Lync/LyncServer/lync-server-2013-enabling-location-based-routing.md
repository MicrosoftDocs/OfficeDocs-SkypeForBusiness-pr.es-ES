---
title: 'Lync Server 2013: habilitar el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b254e7e05a0ac2117b12a0004435898069059f53
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Habilitación del enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-26_

Una vez que se haya implementado la telefonía IP empresarial y se hayan definido las regiones de red, sitios y subredes, puede habilitar el enrutamiento basado en la ubicación. El enrutamiento basado en ubicación debe estar habilitado para los siguientes elementos de Enterprise Voice:

  - Sitios de red

  - Configuraciones de tronco

  - Directivas de voz

  - Configuración de enrutamiento

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Habilitar el enrutamiento basado en ubicación a sitios de red

Una vez que haya implementado Enterprise Voice y los sitios de red configurados, estará preparado para configurar el enrutamiento basado en ubicación. En primer lugar, cree una directiva de enrutamiento de voz para asociar el sitio de red con los usos de RTC apropiados. Al asignar usos de RTC a una directiva de enrutamiento de voz, asegúrese de usar solo los usos de RTC asociados a rutas de voz que usan una puerta de enlace RTC local al sitio o a una puerta de enlace RTC que se encuentra en una región en la que no se necesitan restricciones de enrutamiento basadas en la ubicación. Use el comando de Windows PowerShell de Lync Server, New-CsVoiceRoutingPolicy o el panel de control de Lync Server para crear directivas de enrutamiento de voz.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

En este ejemplo, los siguientes comandos de Windows PowerShell y tabla muestran dos directivas de enrutamiento de voz y sus usos de RTC asociados definidos en este escenario. Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Directiva de enrutamiento de voz 1</th>
<th>Directiva 2 de enrutamiento de voz</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IDENTIFICADOR de la Directiva de voz</p></td>
<td><p>Directiva de enrutamiento de voz de Delhi</p></td>
<td><p>Directiva de enrutamiento de voz de Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de Delhi, PBX del uso, uso de HYD de PBX</p></td>
<td><p>Uso de Hyderabad, uso de HYD de PBX, PBX del uso</p></td>
</tr>
</tbody>
</table>

  

A continuación, configure el enrutamiento basado en ubicación para los sitios de red aplicables y asocie sus directivas de enrutamiento de voz a ellos. Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite, para habilitar el enrutamiento basado en ubicación y asociar directivas de enrutamiento de voz a los sitios de red que deban exigir restricciones de enrutamiento.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

En este ejemplo, la tabla siguiente ilustra el enrutamiento basado en ubicación para dos sitios de red diferentes, Delhi y Hyderabad, definidos en este escenario con Windows PowerShell de Lync Server. Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


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
<td><p>Nombre del sitio </p></td>
<td><p>Sitio 1 (Delhi)</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>Directiva de enrutamiento de voz</p></td>
<td><p>Directiva de enrutamiento de voz de Delhi</p></td>
<td><p>Directiva de enrutamiento de voz de Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Subredes</p></td>
<td><p>Subred 1 (Delhi)</p></td>
<td><p>Subred 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Habilitar el enrutamiento basado en ubicación a troncos

Antes de poder habilitar una configuración de tronco para el enrutamiento basado en ubicación, debe crear una configuración de tronco para cada tronco o cada sitio de red. Use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration, para crear una configuración de tronco. Si hay varios troncos asociados a un sistema determinado (por ejemplo, a una puerta de enlace o PBX), se debe modificar cada configuración de tronco para habilitar las restricciones de enrutamiento basadas en la ubicación.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

En este ejemplo, los siguientes comandos de Windows PowerShell ilustran la creación de una configuración de tronco para cada tronco en la implementación definida en este escenario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Una vez configurada la configuración del tronco por tronco, puede usar el comando de Windows PowerShell de Lync Server, Set-CsTrunkConfiguration, para habilitar el enrutamiento basado en ubicación a los troncos que deben exigir restricciones de enrutamiento. Habilite el enrutamiento basado en ubicación a los troncos que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocien el sitio de red en el que se encuentra la puerta de enlace.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

En este ejemplo, el enrutamiento basado en ubicación está habilitado para todos los tronco asociados a puertas de enlace RTC en Delhi y Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

No habilite el enrutamiento basado en ubicación para troncos que no enruten llamadas a la RTC; sin embargo, debe asociar el tronco al sitio de red donde se encuentra el sistema, ya que las restricciones de enrutamiento basadas en ubicación deben aplicarse para las llamadas RTC que alcanzan los extremos conectados a través de este tronco. Para este ejemplo, el enrutamiento basado en ubicación no está habilitado para todos los tronco asociados a sistemas PBX en Delhi y Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Los extremos que están conectados a sistemas que no enrutan las llamadas a la RTC (es decir, una PBX) tendrán restricciones similares a las de los extremos de Lync de los usuarios habilitados para el enrutamiento basado en ubicación. Esto significa que estos usuarios podrán realizar y recibir llamadas a y desde el usuario de Lync, independientemente de la ubicación del usuario. También podrán realizar llamadas de recepción a y desde otros sistemas que no enruten las llamadas a la red RTC (es decir, un extremo conectado a otra PBX), independientemente del sitio de red al que esté asociado el sistema. Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas con extremos RTC estarán sujetos a las fuerzas de enrutamiento basadas en la ubicación. Estas llamadas deben usar solo puertas de enlace RTC definidas como locales para dichos sistemas.

En la tabla siguiente se muestra la configuración de tronco de cuatro troncos en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway: tronco 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: tronco 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: tronco 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: tronco 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Habilitar el enrutamiento basado en ubicación a directivas de voz

Para aplicar el enrutamiento basado en ubicación a usuarios específicos, configure la Directiva de voz de los usuarios para evitar el desvío de llamadas RTC. Use el comando de Windows PowerShell de Lync Server, New-CsVoicePolicy, para crear una nueva Directiva de voz o set-CsVoicePolicy, si usa una directiva existente, para habilitar el enrutamiento basado en ubicación evitando el desvío de llamadas RTC.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Para obtener más información, vea [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

En este ejemplo, los siguientes comandos de Windows PowerShell y tabla muestran cómo evitar la omisión de peajes RTC en las directivas de voz de Delhi y Hyderabad definidas en este escenario. Solo la configuración específica para el enrutamiento basado en ubicación se incluye en la tabla con fines ilustrativos.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Directiva de voz 1</th>
<th>Directiva de voz 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IDENTIFICADOR de la Directiva de voz</p></td>
<td><p>Directiva de voz de Delhi</p></td>
<td><p>Directiva de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de Delhi, PBX del uso, uso de HYD de PBX</p></td>
<td><p>Uso de Hyderabad, uso de HYD de PBX, PBX del uso</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Habilitar el enrutamiento basado en ubicación en la configuración de enrutamiento

Por último, habilite globalmente el enrutamiento basado en ubicación a la configuración de enrutamiento. Use el comando de Windows PowerShell de Lync Server, New-CsRoutingConfiguration, para habilitar el enrutamiento basado en ubicación.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Para obtener más información, vea [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> Aunque el enrutamiento basado en ubicación debe habilitarse a través de una configuración global, el conjunto de reglas que se aplicará solo se aplicará a los sitios, usuarios y troncos para los que se haya configurado tal y como se especifica en esta documentación.



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración del enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

