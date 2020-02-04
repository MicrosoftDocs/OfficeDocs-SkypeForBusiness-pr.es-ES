---
title: 'Lync Server 2013: Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación'
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
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-06-18_

El enrutamiento basado en la ubicación es exigido por Lync Server. Lync Server puede identificar los sitios de red desde los que se conectan los usuarios dentro de la red corporativa. Dado que los usuarios remotos están fuera de la red corporativa, su ubicación se considera como desconocida.

<div>

## <a name="lync-server-support"></a>Soporte técnico de Lync Server

El enrutamiento basado en la ubicación requiere que Lync Server 2013 CU1 se implemente en todas las agrupaciones front end y servidores Standard Edition en una topología determinada. Si Lync Server 2013 CU1 no está instalado en ciertos componentes de Lync en la topología, las restricciones de enrutamiento basadas en la ubicación no se pueden aplicar por completo.

En la siguiente tabla se identifica la combinación de las versiones y los roles de servidor que se admiten para el enrutamiento basado en la ubicación.


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
<td><p>Lync Server 2013, actualización acumulativa de febrero 2013</p></td>
<td><p>Lync Server 2013, actualización acumulativa de febrero 2013</p></td>
<td><p>sí</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013, actualización acumulativa de febrero 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>no</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013, actualización acumulativa de febrero 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>no</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013, actualización acumulativa de febrero 2013</p></td>
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

La siguiente tabla identifica los clientes que admite el enrutamiento basado en la ubicación.


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
<td><p>Incluidas las actualizaciones acumulativas de Lync 2013 de febrero de 2013</p></td>
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
<td><p>Lync Attendant</p></td>
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
<td><p>El VoIP debe estar deshabilitado para los clientes de Lync Mobile 2013 si lo usan los usuarios con el enrutamiento basado en la ubicación habilitado.</p></td>
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
> Para deshabilitar VoIP para Lync Mobile 2013 clientes, asigne una directiva de movilidad con la configuración, audio/vídeo IP, deshabilitado para todos los usuarios habilitados para el enrutamiento basado en la ubicación. Para obtener más detalles sobre la directiva de movilidad, mira <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

