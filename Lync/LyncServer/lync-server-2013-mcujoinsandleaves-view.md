---
title: 'Lync Server 2013: vista McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a>Vista McuJoinsAndLeaves en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista McuJoinsAndLeaves almacena información sobre los usuarios que se unen y salen de la información de un servidor de conferencia. Cada registro de esta vista contiene detalles de la llamada sobre una combinación de una Unión de usuario o el servidor abandonar y Conferencia. Esta vista se presentó en Microsoft Lync Server 2013.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la instancia de conferencia. Se usa junto con SessionIdSeq para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación para identificar la instancia de la Conferencia. Se usa junto con SessionIdTime para identificar de forma exclusiva una instancia de conferencia. Para obtener más información, vea la <a href="lync-server-2013-conferences-table.md">tabla conferencias en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>El URI del servidor de conferencia al que se conectó el usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>El URI del servidor de conferencia al que se conectó el usuario. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>El URI del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>El tipo de URI del usuario en el que se capturó la información de Unión/salida del servidor de conferencias. Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>El inquilino del usuario en el que se ha capturado la información de Unión/salida del servidor de conferencias. Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>La versión de cliente utilizada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>El cliente usado por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>El nombre de la categoría del cliente usada por el usuario en el que se capturó la información de Unión/salida del servidor de conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Identifica de forma única la combinación de usuarios y dispositivos para los usuarios que tienen iniciada sesión simultáneamente en varios dispositivos.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p>Bit que representa si el usuario es un usuario interno o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en conjunción con SessionIdSeq para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa en conjunción con SessionIdTime para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>VARCHAR (775)</p></td>
<td><p>IDENTIFICACIÓN del cuadro de diálogo SIP de la sesión. El formato es: diálogo; de-etiqueta; to-TAG.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Momento en que el usuario se unió al servidor de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>El momento en que el usuario abandonó el servidor de conferencia.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

