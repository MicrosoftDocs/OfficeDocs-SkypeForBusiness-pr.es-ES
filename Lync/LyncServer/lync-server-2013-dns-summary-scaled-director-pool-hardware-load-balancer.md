---
title: 'Lync Server 2013: Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ed4a3a810e4f1aa2fc5228e61cd68af163c91f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Resumen de DNS-grupo de Director escalado, equilibrador de carga de hardware en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

La siguiente tabla contiene un resumen de los registros DNS necesarios para admitir el director de carga equilibrada de hardware. El rol del Director requiere registros DNS similares como servidor front-end. El número de registros necesarios se refleja en los nombres alternativos de sujeto necesarios en el certificado de director. Diferente del servidor front-end, el grupo de directores no hospeda las cuentas de usuario ni hospeda los servicios de movilidad.

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a>Registros DNS necesarios para el grupo de directores mediante un equilibrador de carga de hardware y el equilibrio de carga de DNS

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ubicación/tipo/puerto</th>
<th>FQDN/Registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Asignado a/Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Dirección</p></td>
<td><p>Registro de host de Director usado para la replicación y la comunicación de servidor a servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Director del grupo de HLB VIP</p></td>
<td><p>Registro de host del grupo de directores de equilibrio de carga de DNS</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director del grupo de HLB VIP</p></td>
<td><p>Protocolo de inicio de sesión (SIP) entrante desde la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director del grupo de HLB VIP</p></td>
<td><p>Servicios web de marcado publicados con equilibrio de carga de hardware desde proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director del grupo de HLB VIP</p></td>
<td><p>Servicios web de reunión publicados con equilibrio de carga desde proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director del grupo de HLB VIP</p></td>
<td><p>Carga de hardware equilibrada publicada y definida por los servicios web externos de vale web de proxy inverso para el grupo de directores</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

