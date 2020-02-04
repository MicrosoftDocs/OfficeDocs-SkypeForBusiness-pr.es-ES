---
title: 'Lync Server 2013: Tabla Conferences'
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
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Tabla Conferences en Lync Server 2013

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
<td><p>Primary</p></td>
<td><p>Hora en que el agente CDR capturó la solicitud de conferencia. Solo se usa como clave principal para identificar de forma exclusiva una instancia de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa junto con <strong>SessionIdTime</strong> para identificar de forma exclusiva una instancia de conferencia. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>URI de la Conferencia. Para obtener más información, consulte la <a href="lync-server-2013-conferenceuris-table.md">tabla ConferenceUris en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>identificador</p></td>
<td><p> </p></td>
<td><p>Útil para las conferencias recurrentes; cada instancia de una conferencia periódica tiene el mismo <strong>ConferenceUri</strong>, pero tendrá un <strong>ConfInstance</strong>diferente.</p></td>
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
<td><p>Extranjero</p></td>
<td><p>Número de identificación para identificar el grupo en el que se capturó la Conferencia. Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>ENT</p></td>
<td><p>Extranjero</p></td>
<td><p>Número de identificación para identificar el URI del organizador de esta conferencia. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fdisableautoindexingonschemaupdate</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Máscara de bits que contiene atributos de conferencia. Los valores posibles son:</p>
<ul>
<li><p>0X01</p></li>
<li><p>Sintética</p></li>
<li><p>Transaccional</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Procesar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Campo interno usado por el servicio de supervisión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


\*Para la mayoría de las sesiones, SessionIdSeq tendrá el valor 1. Si dos sesiones comienzan exactamente al mismo tiempo, la SessionIdSeq para uno será 1, y la otra será 2, y así sucesivamente.

</div>

<span> </span>

</div>

</div>

</div>

