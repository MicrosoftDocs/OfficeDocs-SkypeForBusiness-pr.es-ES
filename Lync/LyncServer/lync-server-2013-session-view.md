---
title: 'Lync Server 2013: vista de sesión'
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
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Vista de sesión de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La vista de sesión almacena información sobre las sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.


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
<td><p>Se hace referencia a ella desde la tabla MediaLine.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de conferencia si se trata de una conferencia o DialogID si se trata de una sesión de punto a punto.</p></td>
</tr>
<tr class="odd">
<td><p>Correlación</p></td>
<td><p>VARCHAR (Max)</p></td>
<td><p>IDENTIFICADOR de correlación de la sesión.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Categoría de cuadro de diálogo; 0 ¿se encuentra Lync Server en la pierna del servidor de mediación; 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Indica si se ha omitido la llamada.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Este campo, si está presente, indica por qué no se omitió una llamada, incluso si los identificadores de omisión coinciden. Para Lync Server, solo se define un valor:</p>
<p>0x0001: identificador de omisión desconocido para el adaptador de red predeterminado</p></td>
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
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de destinatarios de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de identidad afirmada de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de identidad afirmada de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del punto de conexión de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del punto de conexión de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario de la llamada. Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario para el destinatario de la llamada. Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría de agente de usuario para el destinatario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>Prioridad de la llamada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

