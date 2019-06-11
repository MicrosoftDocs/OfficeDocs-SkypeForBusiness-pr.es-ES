---
title: 'Lync Server 2013: Configurar el enrutamiento basado en ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configurar el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-12_

Lync Server 2013 CU1, el enrutamiento basado en la ubicación es una característica de telefonía IP empresarial. El enrutamiento basado en la ubicación es una característica de administración de llamadas que controla cómo Lync Server 2013 CU1 dirige las llamadas. Aplica restricciones sobre si las llamadas se pueden enrutar a destinos de PBX o RTC en función de la ubicación de la persona que llama de Lync. El enrutamiento basado en la ubicación aplica las reglas de autorización de llamadas a llamadas RTC en función de la ubicación de red de la persona que llama. La ubicación de la persona que llama se determina en función del sitio de red asociado a la subred de red en la que está conectada la persona que llama. Configurar el enrutamiento basado en la ubicación requiere implementar primero Enterprise Voice y, a continuación, configurar regiones, sitios y subredes de la red. Esto configura la base para habilitar el enrutamiento basado en la ubicación.

Antes de implementar el enrutamiento basado en la ubicación, primero debe implementar Enterprise Voice y configurar regiones y sitios de red, y asociar subredes de red a los sitios de red. Una vez completado, puede configurar el enrutamiento basado en la ubicación. Para conocer los pasos sobre cómo configurar regiones de red, sitios y subredes, consulte [implementar características avanzadas de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Esta sección le guiará a través de la configuración de enrutamiento basado en la ubicación con el ejemplo siguiente como ilustración.

![Ejemplo de enrutamiento basado en la ubicación de voz empresarial] (images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Ejemplo de enrutamiento basado en la ubicación de voz empresarial")

  
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
<td><p>Lync</p></td>
<td><p>Oficina corporativa de Delhi</p></td>
<td><p>DE-LYNC-1, DE-LYNC-2, DE-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Oficina corporativa de Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Desconocido (es decir, Hotel)</p></td>
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
<td><p>Reconoce</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

La tabla siguiente representa los sistemas que se muestran en este entorno de ejemplo.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistemas</th>
<th>Ubicación</th>
<th>Nombre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Grupo de 2013 de Lync Server CU1</p></td>
<td><p>Cualquiera</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, servidor de mediación</p></td>
<td><p>Cualquiera</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Puerta de enlace PSTN 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Puerta de enlace PSTN 2</p></td>
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
<td><p>RED PBX ROJA</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>En esta sección

  - [Configurar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Implementar regiones, sitios y subredes de la red en Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Habilitar el enrutamiento basado en la ubicación en Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementación de características avanzadas de telefonía empresarial en Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

