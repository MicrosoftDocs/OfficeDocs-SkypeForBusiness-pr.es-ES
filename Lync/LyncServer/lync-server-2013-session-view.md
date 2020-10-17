---
title: 'Lync Server 2013: vista de sesión'
description: 'Lync Server 2013: vista de sesión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545016"
---
# <a name="session-view-in-lync-server-2013"></a>Vista de sesión en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>Se obtiene de la tabla MediaLine.</p></td>
</tr>
<tr class="even">
<td><p>Uri</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</p></td>
</tr>
<tr class="odd">
<td><p>Correlation</p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>Id. de correlación de la sesión.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Categoría del cuadro de diálogo; 0 es Lync Server a la pierna del servidor de mediación; 1 es el servidor de mediación a la puerta de la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Indica si la llamada se pasó o no.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>entero</p></td>
<td><p>Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían. Para Lync Server, solo se define un valor:</p>
<p>0x0001: identificador de omisión desconocido del adaptador de red predeterminado</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Hora de inicio de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del grupo de autores de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del grupo de destinatarios de la llamada</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la identidad afirmada del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la identidad afirmada del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre del extremo del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Cadena de agente de usuario del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario del autor de la llamada. Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario del autor de la llamada. Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Cadena del agente de usuario del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo del agente de usuario del destinatario de la llamada. Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario del destinatario de la llamada. Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>entero</p></td>
<td><p>Prioridad de la llamada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

