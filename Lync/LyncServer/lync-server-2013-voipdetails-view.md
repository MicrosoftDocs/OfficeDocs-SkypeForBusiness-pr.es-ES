---
title: 'Lync Server 2013: vista VoIPDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db65da0af7c34d1121e97436af47750186706b68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a>Vista VoIPDetails en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

La vista VoIPDetails almacena información sobre sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se presentó en Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La vista VoIPDetails contiene todas las columnas de la <A href="lync-server-2013-sessiondetails-view.md">vista SessionDetails de Lync Server 2013</A> , además de las columnas que figuran a continuación.



</div>


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
<td><p><strong>FromPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de teléfono del usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>Teléfono</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de teléfono del usuario que se unió a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario que desconectó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Tipo de URI del usuario que ha desconectado la sesión. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Espacio empresarial del usuario que desconectó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de teléfono del usuario que desconectó la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediación usado por el usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Servidor de mediación usado por el usuario que se unió a la sesión.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Puerta de enlace usada por el usuario que inició la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Puerta de enlace usada por el usuario que se unió a la sesión.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

