---
title: 'Lync Server 2013: rellenar la base de datos de ubicaciones'
description: 'Lync Server 2013: rellenar la base de datos de ubicaciones.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6cf3204795ae2c4f8248517b84d7a5ac1bad0d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543176"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a>Rellenar la base de datos de ubicaciones en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-17_

Para buscar clientes en una red de manera automática, primero es preciso rellenar la base de datos de ubicaciones con un *diagrama de cableado* de red, del cual asigna elementos de red a direcciones postales. Para definir el diagrama de cableado puede usar subredes, puntos de acceso inalámbrico, conmutadores y puertos.

Puede agregar direcciones a la base de datos de ubicaciones una a una, pero también puede incorporar varias de ellas a la vez mediante un archivo en formato .csv con los formatos de columna que se describen en la tabla siguiente.

Si utiliza una puerta de enlace de Número de identificación de ubicación de emergencia (ELIN), incluya el ELIN en el campo **CompanyName** de cada ubicación. Puede incluir varios ELIN para cada ubicación, separándolos por un punto y coma.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento de red</th>
<th>Columnas obligatorias</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Punto de acceso inalámbrico</strong></p></td>
<td><p>&lt;BSSID &gt; , &lt; Description, &gt; &lt; Location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; predirectional &gt; ,...</p>
<p>... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; postdirectional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subred</strong></p></td>
<td><p>&lt;Subnet &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; predirectional &gt; ,...</p>
<p>... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; postdirectional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID &gt; , &lt; PortIDSubType &gt; , &lt; PortID &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; ,...</p>
<p>... &lt; Predirectional &gt; , &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; postdirectional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Switch</strong></p></td>
<td><p>&lt;ChassisID &gt; , &lt; Description &gt; , &lt; Location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; predirectional &gt; ,...</p>
<p>... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; postdirectional &gt; , &lt; City &gt; , &lt; State &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</p></td>
</tr>
</tbody>
</table>


Si no rellena la base de datos de ubicaciones y el valor de **Ubicación obligatoria** de la directiva de ubicación se define en **Sí** o **Declinación de responsabilidades**, el cliente indicará al usuario que especifique una ubicación manualmente.

Para obtener información detallada sobre cómo rellenar la base de datos de ubicaciones, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **Remove-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>Para agregar elementos de red a la base de datos de ubicaciones

1.  Ejecute el cmdlet siguiente para agregar una ubicación de subred a la base de datos de ubicaciones.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Para las puertas de enlace ELIN, escriba el ELIN en el campo CompanyName. Puede incluir más de un ELIN. Por ejemplo:
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de subred mediante un archivo denominado "subnets.csv".
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Ejecute el cmdlet siguiente para agregar ubicaciones inalámbricas a la base de datos de ubicaciones.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones inalámbricas mediante un archivo denominado "waps.csv".
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Ejecute el cmdlet siguiente para agregar ubicaciones de conmutador a la base de datos de ubicaciones.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de conmutadores mediante un archivo denominado "switches.csv".
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Ejecute el cmdlet siguiente para agregar ubicaciones de puertos a la base de datos de ubicaciones.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    El valor predeterminado de PortIDSubType es LocallyAssigned. También se puede usar InterfaceAlias e InterfaceName
    
    También es posible ejecutar los cmdlets siguientes para actualizar en una sola acción las ubicaciones de puertos mediante un archivo denominado "ports.csv".
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

