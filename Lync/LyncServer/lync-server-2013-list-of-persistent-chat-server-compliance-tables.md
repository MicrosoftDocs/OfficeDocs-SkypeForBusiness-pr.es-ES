---
title: 'Lync Server 2013: Lista de tablas de cumplimiento del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d3df9a0bfd5fa4b8b4acdda15ed86940c2572a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

El esquema de base de datos de cumplimiento de chat persistente consta de las siguientes tablas.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tablas de cumplimiento del servidor de chat persistente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabla</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData en Lync Server 2013</a></p></td>
<td><p>Contiene los eventos de cumplimiento que el adaptador configurado aún no ha procesado.</p>
<p>Esta tabla incluye eventos persistentes relacionados con el chat, como mensajes instantáneos y descargas de archivos. (Los eventos de participantes se controlan en la tabla tblComplianceParticipant).</p>
<p>(Los servidores que procesaron los eventos de esta tabla se muestran en la tabla tblComplianceFanout).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout en Lync Server 2013</a></p></td>
<td><p>Contiene los servidores que procesaron un evento de cumplimiento. Esta tabla está estrechamente acoplada a la tabla tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant en Lync Server 2013</a></p></td>
<td><p>Contiene participantes actuales por servicio de chat y por servidor. Se mantiene según los eventos de conformidad con la Unión y la parte recibidos del servicio de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState en Lync Server 2013</a></p></td>
<td><p>Contiene información de estado de cumplimiento para todo el grupo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

