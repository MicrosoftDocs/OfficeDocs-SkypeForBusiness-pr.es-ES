---
title: Vista de Session
TOCTitle: Vista de Session
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49889074
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista de Session

 

_**Última modificación del tema:** 2015-03-09_

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
<td><p>ConferenceURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>ConferenceURI, si se trata de una conferencia, o DialogID, si es una sesión punto a punto.</p></td>
</tr>
<tr class="odd">
<td><p>Correlation</p></td>
<td><p>varchar(max)</p></td>
<td><p>Id. de correlación de la sesión.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Categoría del diálogo; 0 es la sección de Lync Server al servidor de mediación; 1 es la sección del servidor de mediación a la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Indica si la llamada se pasó o no.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían. En Lync Server solo se define un valor:</p>
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
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de autores de la llamada</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de destinatarios de la llamada</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de la identidad afirmada del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de la identidad afirmada del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del extremo del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena del agente de usuario del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo del agente de usuario del autor de la llamada. Para más información, vea <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario del autor de la llamada. Para más información, vea <a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena del agente de usuario del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo del agente de usuario del destinatario de la llamada. Para más información, vea <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario del destinatario de la llamada. Para más información, vea <a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>Prioridad de la llamada.</p></td>
</tr>
</tbody>
</table>

