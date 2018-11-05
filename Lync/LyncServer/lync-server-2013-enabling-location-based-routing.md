---
title: Habilitación del enrutamiento basado en ubicación en Lync Server 2013
TOCTitle: Habilitación del enrutamiento basado en ubicación en Lync Server 2013
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994014(v=OCS.15)
ms:contentKeyID: 52061583
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitación del enrutamiento basado en ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Una vez que se ha implementado Telefonía IP empresarial y se han definido las regiones de red, los sitios y las subredes, puede habilitar el enrutamiento según ubicación. El enrutamiento según ubicación debe habilitarse para los siguientes elementos de Telefonía IP empresarial:

  - Sitios de red

  - Configuraciones del tronco

  - Directivas de voz

  - Configuración de enrutamiento

## Habilitar el enrutamiento según ubicación en sitios de red

Una vez que haya implementado Telefonía IP empresarial y configurado los sitios de red, estará listo para configurar el enrutamiento según ubicación. Primero, cree una directiva de enrutamiento de voz para asociar el sitio de red con los usos adecuados de RTC. Al asignar usos de RTC a una directiva de enrutamiento de voz, asegúrese de utilizar únicamente usos de RTC que estén asociados a rutas de voz que usen una puerta de enlace RTC local para el sitio o una puerta de enlace RTC que se encuentre en una región donde las restricciones de enrutamiento según ubicación no sean necesarias. Use el comando Lync ServerWindows PowerShell, New-CsVoiceRoutingPolicy, o Panel de control de Lync Server para crear directivas de enrutamiento de voz.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Para obtener más información, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoiceRoutingPolicy).

Para este ejemplo, la siguiente tabla y comandos de Windows PowerShell ilustran dos directivas de enrutamiento de voz y sus usos de RTC asociados definidos en este escenario. Solo los parámetros que son específicos al enrutamiento según ubicación se incluyen en la tabla con fines meramente ilustrativos.

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
<td><p>Id. de directiva de voz</p></td>
<td><p>Directiva de enrutamiento de voz Delhi</p></td>
<td><p>Directiva de enrutamiento de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso de Delhi, uso de PBX Del, uso de PBX Hyd</p></td>
<td><p>Uso de Hyderabad, uso dePBX Hyd, uso de PBX Del</p></td>
</tr>
</tbody>
</table>

  

A continuación, configure el enrutamiento según ubicación para los sitios de red pertinentes y asocie las directivas de enrutamiento de voz a ellos. Use el comando de Lync ServerWindows PowerShell, New-CsNetworkSite, para habilitar el enrutamiento según ubicación y asociar directivas de enrutamiento de voz a los sitios de red que deben exigir restricciones de enrutamiento.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

En este ejemplo, la siguiente tabla ilustra el enrutamiento según ubicación para dos sitios de red distintos, Delhi y Hyderabad, definidos en este escenario mediante Lync ServerWindows PowerShell. Solo los parámetros que son específicos al enrutamiento según ubicación se incluyen en la tabla con fines meramente ilustrativos.

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
<td><p>Directiva de enrutamiento de voz Delhi</p></td>
<td><p>Directiva de enrutamiento de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Subredes</p></td>
<td><p>Subred 1 (Delhi)</p></td>
<td><p>Subred 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Habilitar el enrutamiento según ubicación en troncos

Antes de que se pueda habilitar una configuración troncal para el enrutamiento según ubicación, es necesario crear una configuración troncal para cada tronco o cada sitio de red. Use el comando de Lync ServerWindows PowerShell, New-CsTrunkConfiguration, para crear una configuración troncal. Si se asocian varios troncos con un sistema determinado (por ejemplo, puerta de enlace o PBX), cada configuración troncal debe modificarse para habilitar las restricciones de enrutamiento según ubicación.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Para obtener más información, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

Para este ejemplo, los siguientes comandos de Windows PowerShell ilustran la creación de una configuración troncal para cada tronco en la implementación definida en este escenario.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Una vez que una configuración troncal se configura por tronco, puede usar el comando de Lync ServerWindows PowerShell, Set-CsTrunkConfiguration, para habilitar el enrutamiento según ubicación en los troncos que deben exigir restricciones de enrutamiento. Habilite el enrutamiento según ubicación en los troncos que enrutan llamadas a puertas de enlace RTC que enrutan las llamadas a RTC y asocie el sitio de red donde se encuentra la puerta de enlace.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Para obtener más información, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

En este ejemplo, el enrutamiento según ubicación se habilita para cada tronco asociado a las puertas de enlace RTC en Delhi y Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

No habilite el enrutamiento según ubicación para los troncos que no enrutan llamadas a RTC. Sin embargo, aún debe asociar el tronco al sitio de red donde se encuentra el sistema, ya que las restricciones de enrutamiento según ubicación necesitan exigirse para las llamadas RTC que alcanzan extremos conectados a través de este tronco. En este ejemplo, el enrutamiento según ubicación no está habilitado para cada tronco asociado a los sistemas PBX en Delhi y Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Los extremos conectados a sistemas que no enrutan llamadas a RTC (es decir, un PBX) tendrán restricciones similares que los extremos de Lync de los usuarios habilitados para el enrutamiento según ubicación. Esto significa que dichos usuarios podrán hacer y recibir llamadas hacia y desde el usuario de Lync independientemente de la ubicación del usuario. También podrán hacer y recibir llamadas hacia y desde otros sistemas que no enrutan llamadas a la red RTC (por ejemplo, un extremo conectado a otro PBX) independientemente del sitio de red al que se asocia el sistema. Todas las llamadas entrantes, llamadas salientes, transferencias de llamadas y reenvío de llamadas que impliquen extremos RTC estarán sujetas a aplicaciones de enrutamiento según ubicación. Dichas llamadas deben usar únicamente puertas de enlace RTC definidas como locales para dichos sistemas.

En la siguiente tabla se ilustra la configuración troncal de cuatro troncos en dos sitios de red distintos: dos conectados a puertas de enlace RTC y dos conectados a sistemas PBX.


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
<td><p>PstnGateway:Trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway:Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Sitio 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Sitio 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Habilitar el enrutamiento según ubicación en directivas de voz

Para exigir el enrutamiento según ubicación para usuarios específicos, configure la directiva de voz de dichos usuarios para impedir la omisión de tarifas RTC. Use el comando de Lync ServerWindows PowerShell, New-CsVoicePolicy, para crear una nueva directiva de voz o Set-CsVoicePolicy, si usa una directiva existente, para habilitar el enrutamiento según ubicación impidiendo la omisión de tarifas RTC.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Para obtener más información, consulte [New-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoicePolicy).

Para este ejemplo, la siguiente tabla y comandos de Windows PowerShell ilustran la habilitación para impedir la omisión de tarifas RTC para las directivas de voz de Delhi y Hyderabad definidas en este escenario. Solo los parámetros que son específicos al enrutamiento según ubicación se incluyen en la tabla con fines meramente ilustrativos.

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
<td><p>Id. de directiva de voz</p></td>
<td><p>Directiva de voz Delhi</p></td>
<td><p>Directiva de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de RTC</p></td>
<td><p>Uso Delhi, uso PBX Del, uso PBX Hyd</p></td>
<td><p>Uso Hyderabad, uso PBX Hyd, uso PBX Del</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>



## Habilitar el enrutamiento según ubicación en la configuración de enrutamiento

Por último, habilite globalmente el enrutamiento según ubicación en la configuración de enrutamiento. Use el comando de Lync ServerWindows PowerShell, New-CsRoutingConfiguration, para habilitar el enrutamiento según ubicación.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Para obtener más información, consulte [Set-CsRoutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRoutingConfiguration).


> [!NOTE]
> Mientras que el enrutamiento según ubicación debe habilitarse a través de una configuración global, el conjunto de reglas que deben aplicarse se exigirá únicamente para los sitios, usuarios y troncos para los que se ha configurado, tal como se especifica en esta documentación.




## Vea también

#### Otros recursos

[Configurar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

