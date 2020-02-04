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
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>tblComplianceParticipant en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-12_

tblComplianceParticipant contiene los participantes actuales por canal y por servidor.

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
<td><p>nvarchar (255), not null</p></td>
<td><p>Identificador uniforme de recursos (URI) del canal.</p></td>
</tr>
<tr class="even">
<td><p>Iddeusuario</p></td>
<td><p>int, not null</p></td>
<td><p>IDENTIFICADOR principal del participante (correspondiente a la tabla tblPrincipal. prinID).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>BIGINT, not null</p></td>
<td><p>Marca de tiempo del evento de Unión.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>BIGINT</p></td>
<td><p>NULL si el participante aún se ha unido. Marca de tiempo del canal dejando el evento si no es NULL.</p>
<p>Estas entradas se eliminan en algún momento cuando todos los traductores procesan el evento.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255), not null</p></td>
<td><p>URI de usuario.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>Identidad del servidor (como en la tabla tblServerIdentity. serverID).</p></td>
</tr>
<tr class="odd">
<td><p>Identificador</p></td>
<td><p>BIGINT</p></td>
<td><p>Sesión de servidor. Este es un número aleatorio generado cada vez que se inicia un servicio de chat. Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Clave

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

