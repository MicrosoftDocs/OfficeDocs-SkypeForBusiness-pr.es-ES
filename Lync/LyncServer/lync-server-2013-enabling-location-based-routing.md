---
title: 'Lync Server 2013: habilitar el enrutamiento basado en la ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170ca1af77a84b655e90d5587fcd101cccf83c8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Habilitar el enrutamiento basado en la ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-04-26_

Una vez que se implementa la telefonía IP empresarial y se definen las regiones, sitios y subredes de la red, puede habilitar el enrutamiento basado en la ubicación. El enrutamiento basado en la ubicación debe estar habilitado para los siguientes elementos de Enterprise Voice:

  - Sitios de red

  - Configuraciones troncales

  - Directivas de voz

  - Configuración de enrutamiento

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Habilitar el enrutamiento basado en ubicación a sitios de red

Una vez que haya implementado Enterprise Voice y los sitios de red configurados, estará listo para configurar el enrutamiento basado en la ubicación. En primer lugar, cree una directiva de enrutamiento de voz para asociar el sitio de red a los usos de RTC apropiados. Al asignar usos de RTC a una directiva de enrutamiento de voz, asegúrese de usar solo usos de RTC asociados a rutas de voz que usen una puerta de enlace PSTN local para el sitio o una puerta de enlace RTC que se encuentre en una región donde no se necesiten restricciones de enrutamiento basado en la ubicación. Use el comando de Windows PowerShell de Lync Server, New-CsVoiceRoutingPolicy o panel de control de Lync Server para crear directivas de enrutamiento de voz.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

En este ejemplo, los siguientes comandos de tabla y Windows PowerShell ilustran dos directivas de enrutamiento de voz y sus usos de RTC asociados definidos en este escenario. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

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
<th>Directiva de enrutamiento de voz 2</th>
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
<td><p>Uso de la Delhi, PBX del uso, uso de HYD de PBX</p></td>
<td><p>Uso de Hyderabad, uso de HYD de PBX, PBX del uso</p></td>
</tr>
</tbody>
</table>

  

A continuación, configure el enrutamiento basado en la ubicación para los sitios de red aplicables y asocie sus directivas de enrutamiento de voz. Use el comando de Windows PowerShell de Lync Server, New-CsNetworkSite, para habilitar el enrutamiento basado en la ubicación y asociar directivas de enrutamiento de voz a los sitios de red que deban exigir restricciones de enrutamiento.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

En este ejemplo, la tabla siguiente muestra el enrutamiento basado en la ubicación de dos sitios de red diferentes, Delhi y Hyderabad, definidos en este escenario con Windows PowerShell de Lync Server. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

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
<td><p>Nombre del sitio</p></td>
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

## <a name="enable-location-based-routing-to-trunks"></a>Habilitar el enrutamiento basado en la ubicación a los troncos

Antes de poder habilitar una configuración de tronco para el enrutamiento basado en la ubicación, debe crear una configuración troncal para cada troncal o cada sitio de red. Use el comando de Windows PowerShell de Lync Server, New-CsTrunkConfiguration, para crear una configuración troncal. Si hay varios troncos asociados con un sistema determinado (por ejemplo, puerta de enlace o PBX), cada configuración de troncal debe modificarse para habilitar las restricciones de enrutamiento basadas en la ubicación.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

En este ejemplo, los siguientes comandos de Windows PowerShell ilustran la creación de una configuración de tronco para cada tronco de la implementación definida en este escenario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Una vez configurada la configuración del tronco por tronco, puede usar el comando de Windows PowerShell de Lync Server, Set-CsTrunkConfiguration, para habilitar el enrutamiento basado en la ubicación a sus troncos que deben exigir restricciones de enrutamiento. Habilite el enrutamiento basado en la ubicación a los troncos que enruten las llamadas a puertas de enlace RTC que enruten las llamadas a la RTC y asocie el sitio de red donde se encuentra la puerta de enlace.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Para obtener más información, vea [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

En este ejemplo, el enrutamiento basado en la ubicación está habilitado para cada tronco asociado a las puertas de enlace RTC de Delhi y Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

No habilite el enrutamiento basado en la ubicación para los troncos que no enruten las llamadas a la RTC; sin embargo, todavía debe asociar el tronco al sitio de red donde se encuentra el sistema, ya que es necesario exigir restricciones de enrutamiento basado en la ubicación para las llamadas RTC que llegan a los puntos de conexión conectados a través de este tronco. En este ejemplo, el enrutamiento basado en la ubicación no está habilitado para cada tronco asociado a sistemas PBX en Delhi y Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Los puntos de conexión que estén conectados a sistemas que no enruten llamadas a la RTC (es decir, una PBX) tendrán restricciones similares a las de los extremos de Lync de los usuarios habilitados para el enrutamiento basado en la ubicación. Esto significa que estos usuarios podrán realizar y recibir llamadas a y desde el usuario de Lync independientemente de la ubicación del usuario. También podrán realizar llamadas recibidas a otros sistemas y desde otros sistemas que no enruten las llamadas a la red RTC (es decir, un extremo conectado a otro PBX), independientemente del sitio de red al que esté asociado el sistema. Todas las llamadas entrantes, las llamadas salientes, las transferencias de llamadas y el desvío de llamadas con puntos de conexión RTC estarán sujetos a las fuerzas de enrutamiento basadas en la ubicación. Dichas llamadas deben usar solo puertas de enlace RTC que estén definidas como locales para esos sistemas.

En la tabla siguiente se muestra la configuración troncal de cuatro troncos en dos sitios de red diferentes: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.


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
<td><p>PstnGateway: troncal 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: Troncal 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: troncal 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: troncal 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Habilitar el enrutamiento basado en la ubicación a directivas de voz

Para aplicar el enrutamiento basado en la ubicación a usuarios específicos, configure la Directiva de voz de los usuarios para evitar la omisión de llamadas RTC. Use el comando de Windows PowerShell de Lync Server, New-CsVoicePolicy, para crear una nueva Directiva de voz o set-CsVoicePolicy, si usa una directiva existente, para habilitar el enrutamiento basado en la ubicación evitando la omisión de llamadas RTC.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Para obtener más información, vea [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

En este ejemplo, los siguientes comandos de tabla y Windows PowerShell ilustran la prevención de la omisión de llamadas RTC en las directivas de voz de Delhi y Hyderabad definidas en este escenario. En la tabla solo se incluyen los valores específicos del enrutamiento basado en la ubicación con fines de ilustración.

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
<th>Política de voz 1</th>
<th>Política de voz 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IDENTIFICADOR de la Directiva de voz</p></td>
<td><p>Directiva de voz de Delhi</p></td>
<td><p>Política de voz de Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de la Delhi, PBX del uso, uso de HYD de PBX</p></td>
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

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Habilitar el enrutamiento basado en la ubicación en la configuración de enrutamiento

Por último, habilite globalmente el enrutamiento basado en la ubicación a la configuración de enrutamiento. Use el comando de Windows PowerShell de Lync Server, New-CsRoutingConfiguration, para habilitar el enrutamiento basado en la ubicación.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Para obtener más información, consulte [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> Si bien el enrutamiento basado en la ubicación debe habilitarse a través de una configuración global, el conjunto de reglas que se aplicará solo se aplicará a los sitios, usuarios y troncos para los que se haya configurado tal como se especifica en esta documentación.



</div>

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

