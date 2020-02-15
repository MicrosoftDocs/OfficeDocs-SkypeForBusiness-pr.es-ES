---
title: 'Lync Server 2013: vista de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7418c5aa80e35d783517a86626dd2b77a393e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a>Vista de registro en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

La vista de registro almacena información sobre el registro de usuarios. Esta vista se introdujo en Lync Server 2013.


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
<td><p>Hora de la solicitud de sesión. Se usa de forma conjunta con SessionIdSeq para identificar de forma exclusiva una sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Número de identificador para identificar la sesión. Se usa de forma conjunta con SessionIdTime para identificar de forma exclusiva una sesión. Consulte la <a href="lync-server-2013-dialogs-table.md">tabla de cuadros de diálogo en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que ocurrió el registro.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del usuario que se registró.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Tipo de URI del usuario que se registró. Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Inquilino del usuario que se registró. Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único del extremo con el que se registró el usuario.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>identificador</p></td>
<td><p>Identificador único que se utiliza para diferenciar los registros con el mismo usuario y el mismo extremo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>Hora a la que ocurrió la anulación de registro.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Motivo de la anulación de registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versión del cliente que utilizó el usuario que se registró.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Cliente que utilizó el usuario que se registró. Consulte la <a href="lync-server-2013-useragentdef-table.md">tabla UserAgentDef en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del cliente que utilizó el usuario que se registró.</p></td>
</tr>
<tr class="even">
<td><p><strong>DirIP</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Dirección IP con la que se registró el usuario. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Identificador</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>Identificador del diálogo SIP. El formato es:</p>
<p>Dialog; from-Tag; to-Tag</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Código de respuesta SIP a la invitación a la sesión. Este campo se suele rellenar con datos generados a partir del mensaje INVITE inicial de la sesión. Si no hay ningún mensaje INVITE, el campo se rellena con la hora y la fecha del primer mensaje SIP correspondiente (BYE, CANCEL, MESSAGE o INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>Identificador de diagnóstico capturado del encabezado SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dominios</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del registrador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del grupo de servidores que capturó los datos de la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del servidor perimetral que utilizó el usuario que se registró.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el usuario inició sesión desde la red interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el UserService estaba disponible en el momento del registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p>Indica si el registro se realizó con el registrador principal.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>BIGINT</p></td>
<td><p>Dirección MAC del dispositivo registrado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Fabricante del dispositivo registrado. Consulte la <a href="lync-server-2013-manufacturers-table.md">tabla fabricantes en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Versión del hardware del dispositivo registrado. Consulte la <a href="lync-server-2013-hardwareversions-table.md">tabla HardwareVersions en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

