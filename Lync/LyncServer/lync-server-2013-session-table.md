---
title: 'Lync Server 2013: Tabla Session'
TOCTitle: Tabla Session
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48275817
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla Session en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa una sesión en la que hay audio o audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un diálogo de Protocolo de inicio de sesión (SIP) de audio o vídeo entre dos extremos.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-dialog-table.md">Tabla Dialog en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-dialog-table.md">Tabla Dialog en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Clave de la conferencia. Con referencia a la <a href="lync-server-2013-conference-table.md">Tabla Conference en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Clave de correlación. Se obtiene de la <a href="lync-server-2013-sessioncorrelation-table.md">Tabla SessionCorrelation en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Categoría del diálogo; 0 es la sección de Lync Server al servidor de mediación; 1 es la sección del servidor de mediación a la puerta de enlace RTC.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Marca que indica si la llamada se pasó o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Este campo (si existe) indica por qué la llamada no se pasó, aun cuando los identificadores de omisión coincidían. En Lync Server solo se define un valor.</p>
<p>0x0001: identificador de omisión desconocido del adaptador de red predeterminado.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p> </p></td>
<td><p>Hora de inicio de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p> </p></td>
<td><p>Hora de finalización de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Grupo del autor de la llamada. Con referencia a la <a href="lync-server-2013-pool-table.md">Tabla Pool en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Grupo del destinatario de la llamada. Con referencia a la <a href="lync-server-2013-pool-table.md">Tabla Pool en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI de SIP en la identidad p-asserted (PAI) de SIP del extremo receptor. Con referencia a la <a href="lync-server-2013-user-table.md">Tabla User en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI del autor de la llamada. Con referencia a la <a href="lync-server-2013-user-table.md">Tabla User en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Extremo del autor de la llamada. Con referencia a la <a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>Externa</p></td>
<td><p>Agente de usuario del autor de la llamada. Con referencia a la <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Prioridad de esta llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Esta columna se desusará y no se utilizará en Microsoft Lync Server 2013. En su lugar, esta información se informa según cada medio. Vea el <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>La identidad p-asserted del usuario que realizó la llamada. La identidad p-asserted (PAI) se utiliza para revelar la verdadera identidad del usuario que realizó la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Extremo que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Agente de usuario empleado por el usuario que recibió la llamada. Los agentes de usuario representan el dispositivo en el extremo del cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>URI SIP del usuario que recibió la llamada.</p></td>
</tr>
</tbody>
</table>

