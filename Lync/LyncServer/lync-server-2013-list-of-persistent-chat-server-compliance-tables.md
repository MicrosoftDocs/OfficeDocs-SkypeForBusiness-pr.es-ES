---
title: 'Lync Server 2013: lista de tablas de cumplimiento del servidor de chat persistente'
description: 'Lync Server 2013: lista de tablas de cumplimiento del servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550076"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lista de tablas de cumplimiento del servidor de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

El esquema de la base de datos de cumplimiento de chat persistente consta de las siguientes tablas.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Lista de tablas de cumplimiento del servidor de chat persistente


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData en Lync Server 2013</a></p></td>
<td><p>Contiene los eventos de cumplimiento que aún no fueron procesados por el adaptador configurado.</p>
<p>Esta tabla incluye eventos relacionados con el chat persistente, como mensajes de chat y descargas de archivos. (Los eventos participantes son seguidos por la tabla tblComplianceParticipant).</p>
<p>(Los servidores que procesaron los eventos en esta tabla se enumeran en la tabla tblComplianceFanout).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout en Lync Server 2013</a></p></td>
<td><p>Contiene los servidores que procesaron un evento de cumplimiento. Esta tabla está fuertemente vinculada con la tabla tblComplianceData.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant en Lync Server 2013</a></p></td>
<td><p>Contiene los participantes actuales por servicio de chat y por servidor. Se mantiene en función de los eventos de conformidad de Unión y parte recibidos del servicio de chat persistente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState en Lync Server 2013</a></p></td>
<td><p>Contiene información de estado de cumplimiento de todo el grupo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

