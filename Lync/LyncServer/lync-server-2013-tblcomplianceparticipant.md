---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6ce992f7a36bd5ce731f26dcb5dbfac0e2acae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509437"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>tblComplianceParticipant en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.

### <a name="columns"></a>Columnas

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelUri</p></td>
<td><p>nvarchar (255), no NULL</p></td>
<td><p>Identificador uniforme de recursos (URI) del canal.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, no NULL</p></td>
<td><p>Identificador de la entidad de seguridad del participante (correspondiente a la tabla tblPrincipal.prinID).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, no NULL</p></td>
<td><p>Marca de tiempo del evento participante.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>BIGINT</p></td>
<td><p>Nulo si el participante aún está participando. La marca de tiempo del canal que abandona el evento si no es nulo.</p>
<p>Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar(255), no NULL</p></td>
<td><p>URI del usuario.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>entero</p></td>
<td><p>Identidad del servidor (como en la tabla tblServerIdentity.serverID).</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>BIGINT</p></td>
<td><p>Sesión del servidor. Es un número aleatorio que se genera cada vez que se inicia un servicio de chat. Sirve para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key 

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>Clave principal.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

