---
title: 'Lync Server 2013: Tabla Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Tabla Session en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-09-09_

Cada registro representa una sesión que incluye audio, audio y vídeo. Contiene información general sobre la sesión. Una sesión se define como un cuadro de diálogo de protocolo de inicio de sesión (SIP) de audio o vídeo entre dos puntos de conexión.


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
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-dialog-table.md">tabla de diálogo en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-dialog-table.md">tabla de diálogo en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Tecla de conferencia. Se hace referencia a ellos desde la <a href="lync-server-2013-conference-table.md">tabla de conferencia en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Clave de correlación. Se hace referencia a ellos desde la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Categoría de cuadro de diálogo; 0 ¿se encuentra Lync Server en la pierna del servidor de mediación; 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Marcador que indica si la llamada se ha omitido o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Este campo, si está presente, indica por qué no se omitió una llamada, incluso si los identificadores de omisión coinciden. Para Lync Server, solo se define un valor.</p>
<p>0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de inicio de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Hora de finalización de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>El grupo de la persona que llama. Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla de grupos en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>La piscina del receptor de la llamada. Se hace referencia a ella desde la <a href="lync-server-2013-pool-table.md">tabla de grupos en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>URI de SIP en la identidad declarada por SIP (PAI) del punto final de recepción. Se hace referencia a ellos desde la <a href="lync-server-2013-user-table.md">tabla de usuario en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>URI de la persona que llama. Se hace referencia a ellos desde la <a href="lync-server-2013-user-table.md">tabla de usuario en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Extremo de la persona que llama. Se hace referencia a ellos desde la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>Extranjero</p></td>
<td><p>Agente de usuario del autor de la llamada. Se hace referencia a ella desde la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>La prioridad de esta llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Esta columna ha quedado obsoleta y no se usa en Microsoft Lync Server 2013. En su lugar, esta información se notifica en una base de líneas por medios. Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>P-asserted-identidad del usuario que realizó la llamada. La identidad de aserción de P (PAI) se usa para transmitir la verdadera identidad del usuario que realizó la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Extremo que recibió la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Agente de usuario empleado por el usuario que recibió la llamada. Los agentes de usuario representan el dispositivo de extremo cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>URI SIP del usuario que recibió la llamada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

