---
title: 'Lync Server 2013: Resumen de DNS-Director único'
description: 'Lync Server 2013: Resumen de DNS-Director único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553236"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a>Resumen de DNS-Director único en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

La siguiente tabla contiene un resumen de los registros DNS necesarios para admitir el director único. El rol del Director requiere registros DNS similares como servidor front-end. El número de registros necesarios se refleja en los nombres alternativos de sujeto necesarios en el certificado de director. Diferente del servidor front-end, el director no hospeda cuentas de usuario ni hospeda los servicios de movilidad.

### <a name="dns-records-required-for-the-director"></a>Registros DNS necesarios para el director

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
<td><p>Director</p></td>
<td><p>Registro de host de Director usado para la replicación y el servidor a servidor</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Protocolo de inicio de sesión (SIP) entrante de la interfaz perimetral interna del servidor perimetral</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Servicios Web de marcado publicados desde el proxy inverso</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Se publicaron los servicios web desde el proxy inverso</p></td>
</tr>
<tr class="odd">
<td><p>DNS interno/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Publicado y definido por los servicios web externos de vale Web de proxy inverso para el director</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

