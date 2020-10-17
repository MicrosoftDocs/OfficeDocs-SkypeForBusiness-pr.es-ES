---
title: 'Lync Server 2013: configurar el enrutamiento de Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517424"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configuración del enrutamiento de Location-Based en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

Lync Server 2013 CU1, Location-Based Routing es una característica de Enterprise Voice. El enrutamiento Location-Based es una característica de administración de llamadas que controla cómo se enrutan las llamadas por parte de Lync Server 2013 CU1. Aplica restricciones en cuanto a si las llamadas se pueden enrutar a los destinos de PBX o RTC en función de la ubicación del autor de la llamada de Lync. El enrutamiento Location-Based se aplica a las reglas de autorización de llamadas a RTC en función de la ubicación de red del autor de la llamada. La ubicación del autor de la llamada se determina en función del sitio de red asociado a la subred de red en la que está conectado el autor de la llamada. La configuración del enrutamiento de Location-Based requiere que se implemente primero la telefonía IP empresarial y, a continuación, la configuración de regiones de red, sitios y subredes. De esta forma se establece la base para habilitar el enrutamiento de Location-Based.

Antes de implementar el enrutamiento de Location-Based, primero debe implementar Enterprise Voice y configurar regiones de red, sitios y asociar subredes de red a los sitios de red. Una vez completada, puede configurar el enrutamiento de Location-Based. Para conocer los pasos necesarios para configurar regiones de red, sitios y subredes, vea [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Esta sección le guiará a través de la configuración del enrutamiento de Location-Based mediante el siguiente ejemplo como ilustración.

![Ejemplo de enrutamiento basado en Enterprise Voice Location](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Ejemplo de enrutamiento basado en Enterprise Voice Location")

  
En la tabla siguiente se representan los usuarios definidos en este ejemplo.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de extremo</th>
<th>Ubicación</th>
<th>Usuarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2015</p></td>
<td><p>Oficina corporativa de Delhi</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>2015</p></td>
<td><p>Oficina corporativa de Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>2015</p></td>
<td><p>Desconocido (por ejemplo, Hotel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Oficina corporativa de Delhi</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Oficina corporativa de Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>RTC</p></td>
<td><p>Unknown</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

La siguiente tabla representa los sistemas que se ilustran en este entorno de ejemplo.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema</th>
<th>Ubicación</th>
<th>Nombre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Grupo de servidores de Lync Server 2013 CU1</p></td>
<td><p>cualquiera</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, servidor de mediación</p></td>
<td><p>cualquiera</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Puerta de enlace RTC 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Puerta de enlace RTC 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>PBX ROJA</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Implementar regiones de red, sitios y subredes en Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Habilitación del enrutamiento Location-Based en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

