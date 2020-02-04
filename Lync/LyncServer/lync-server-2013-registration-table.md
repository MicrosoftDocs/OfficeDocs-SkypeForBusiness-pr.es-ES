---
title: 'Lync Server 2013: Tabla Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bc19c35893b12aae7842be5fc474f7831b7f979
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Tabla Registration en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-28_

Cada registro representa un evento de registro de usuario.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Columna</th>
<th>Tipo de datos</th>
<th>Clave o índice</th>
<th>Detalles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Hora de la solicitud de sesión. Se usa en conjunción con <strong>SessionIdSeq</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Número de identificación para identificar la sesión. Se usa en conjunción con <strong>SessionIdTime</strong> para identificar de forma única una sesión. Para obtener más información, vea la <a href="lync-server-2013-dialogs-table.md">tabla cuadros de diálogo en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Iddeusuario</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>El identificador de usuario. Para obtener más información, consulte la <a href="lync-server-2013-users-table.md">tabla usuarios en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>identificador</p></td>
<td></td>
<td><p>Un GUID para identificar un extremo de registro. Normalmente, el evento Register del mismo equipo del mismo usuario tendrá el mismo identificador de punto de conexión. Diferentes equipos tienen un identificador de extremo diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>Identificador</p></td>
<td></td>
<td><p>IDENTIFICADOR usado para diferenciar los registros que implican el mismo usuario y el mismo punto de conexión.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Versión de cliente del usuario actual. Para obtener más información, consulte la <a href="lync-server-2013-clientversions-table.md">tabla ClientVersions en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del servidor del registrador usado para el registro. Para obtener más información, consulte la <a href="lync-server-2013-servers-table.md">tabla servidores en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>IDENTIFICADOR del grupo en el que se capturó la sesión. Para obtener más información, consulte la <a href="lync-server-2013-pools-table.md">tabla de grupos en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Servidor perimetral en el que se está realizando la inscripción. Para obtener más información, consulte la <a href="lync-server-2013-edgeservers-table.md">tabla EdgeServers en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Algo</p></td>
<td></td>
<td><p>Si el usuario ha iniciado sesión desde dentro o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si el UserService está disponible o no.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si se registra en el registrador principal o no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica si el usuario está registrado o no en un equipo de sucursal con la supervivencia.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora de registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>Hora de Desregistro.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Código de respuesta de la solicitud de registro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>IDENTIFICADOR de diagnóstico de la solicitud de registro. Indica que el tipo de información de diagnóstico.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>El dispositivo del que procede la solicitud de registro. Para obtener más información, consulte la <a href="lync-server-2013-devices-table.md">tabla dispositivos en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Extranjero</p></td>
<td><p>El motivo de la anulación del registro, como "Iniciado por el usuario", "registro expirado", "error del cliente" y más. Para obtener más información, consulte la <a href="lync-server-2013-deregistertype-table.md">tabla DeRegisterType en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Dirección IP del extremo con el que el usuario registró el registro. Puede ser una dirección IPv4 o una dirección IPv6.</p>
<p>Este campo se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

