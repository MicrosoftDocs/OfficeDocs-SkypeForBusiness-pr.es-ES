---
title: 'Lync Server 2013: Resumen de DNS - Carga equilibrada DNS y HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>Resumen de DNS - Carga equilibrada DNS y HLB en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

La tabla siguiente contiene un resumen de los registros DNS necesarios para admitir el equilibrio de carga de hardware y equilibrio de carga de DNS. La función del Director requiere registros DNS similares como servidor front-end. El número de registros necesarios se refleja en el asunto nombres alternativos requeridos en el certificado de director. Diferente al servidor front-end, el grupo de directores no hospeda cuentas de usuario ni hospeda los servicios de movilidad.

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a>Registros DNS necesarios para el grupo de directores mediante el equilibrio de carga de DNS y el equilibrador de carga de hardware

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
<th>FQDN/registro DNS</th>
<th>Dirección IP/FQDN</th>
<th>Se asigna a/comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A interno</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Registro de host de Director usado para la replicación y el servidor a servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>Grupo de directores</p></td>
<td><p>Registro de host para el grupo de directores de carga equilibrada de DNS para servidor a servidor</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A interno</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Grupo de directores</p></td>
<td><p>Protocolo de inicio de sesión (SIP) entrante de la interfaz interna del servidor perimetral</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Grupo de directores HLB VIP</p></td>
<td><p>Equilibrio de carga de hardware publicado servicios Web de marcado desde proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A interno</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Grupo de directores HLB VIP</p></td>
<td><p>El equilibrio de carga de hardware publicado cumple con los servicios web del proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Grupo de directores HLB VIP</p></td>
<td><p>Equilibrio de carga de hardware publicado y definido por el vale Web de proxy inverso servicios web externos para el grupo de directores</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

