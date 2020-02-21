---
title: 'Lync Server 2013: tabla de conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3dbaf1a721433cc04aa681dad56d753de8bc9a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Tabla conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cada registro de esta tabla contiene detalles de llamadas sobre una conferencia.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Hora en que el agente CDR capturó la solicitud de conferencia. Solo se usa como clave principal para identificar de forma única una instancia de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Número de identificador para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> para identificar de forma única una instancia de conferencia. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>URI de conferencia. Consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>identificador</p></td>
<td><p> </p></td>
<td><p>Útil para las conferencias recurrentes; cada instancia de una conferencia periódica tiene la misma <strong>URI</strong>, pero tendrá un <strong>ConfInstance</strong>diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de inicio de la Conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de inicio de la Conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Externa</p></td>
<td><p>Número de identificador para identificar el grupo de servidores en el que se capturó la Conferencia. Consulte la <a href="lync-server-2013-pools-table.md">tabla grupos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número de identificador para identificar el URI del organizador de esta conferencia. Consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Máscara de bits que contiene los atributos de la Conferencia. Los valores posibles son:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Vitaminas</p></li>
<li><p>Transacción</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Procesan</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Campo interno usado por el servicio de supervisión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor de 1. Si dos sesiones comienzan exactamente al mismo tiempo, el SessionIdSeq para uno será 1, y el otro será 2, y así sucesivamente.

</div>

<span> </span>

</div>

</div>

</div>

