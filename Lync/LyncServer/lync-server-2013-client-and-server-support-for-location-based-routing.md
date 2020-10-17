---
title: 'Lync Server 2013: compatibilidad del cliente y el servidor con el enrutamiento Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529347"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Compatibilidad de cliente y servidor para el enrutamiento Location-Based en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-18_

El enrutamiento de Location-Based es aplicado por Lync Server. Lync Server puede identificar los sitios de red desde los que se conectan los usuarios de la red corporativa. Como los usuarios remotos están fuera de la red corporativa, se considera que su ubicación es desconocida.

<div>

## <a name="lync-server-support"></a>Compatibilidad con Lync Server

El enrutamiento Location-Based requiere que Lync Server 2013 CU1 se implemente en todos los grupos de servidores front-end y servidores Standard Edition en una topología determinada. Si Lync Server 2013 CU1 no está instalado en determinados componentes de Lync en la topología, Location-Based restricciones de enrutamiento no se pueden aplicar completamente.

En la siguiente tabla se identifica la combinación de roles de servidor y versiones compatibles con el enrutamiento Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Versión del grupo</th>
<th>Versión del servidor de mediación</th>
<th>Compatible</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 a la actualización acumulativa de febrero de 2013</p></td>
<td><p>Lync Server 2013 a la actualización acumulativa de febrero de 2013</p></td>
<td><p>sí</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 a la actualización acumulativa de febrero de 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 a la actualización acumulativa de febrero de 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 a la actualización acumulativa de febrero de 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>cualquiera</p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>cualquiera</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>cualquiera</p></td>
<td><p>no</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Compatibilidad con clientes de Lync

En la tabla siguiente se identifican los clientes compatibles con el enrutamiento de Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de cliente</th>
<th>Compatible</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>sí</p></td>
<td><p>Inclusión de la actualización acumulativa de Lync 2013 febrero de 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>no</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Operador de Lync</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync para Windows 8</p></td>
<td><p>no</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>no</p></td>
<td><p>VoIP debe estar deshabilitado para los clientes de Lync Mobile 2013 si lo usan los usuarios con el enrutamiento de Location-Based habilitado.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>sí</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Para deshabilitar VoIP para los clientes de Lync Mobile 2013, asigne una directiva de movilidad con la configuración, audio/vídeo IP, deshabilitado para todos los usuarios habilitados para el enrutamiento basado en ubicación. Para obtener más información sobre la Directiva de movilidad, vea <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Planeación del enrutamiento de Location-Based en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

