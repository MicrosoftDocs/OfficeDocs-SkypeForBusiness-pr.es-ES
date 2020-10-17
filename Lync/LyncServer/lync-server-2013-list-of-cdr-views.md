---
title: 'Lync Server 2013: lista de vistas de CDR'
description: 'Lync Server 2013: lista de vistas de CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550086"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lista de vistas de CDR en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Las vistas proporcionan una manera sencilla de acceder a la información sobre los escenarios más comunes utilizados para devolver datos de la base de datos de CDR. Se recomienda usar vistas para crear informes personalizados en lugar de usar las tablas de base de datos de CDR reales; Esto se debe a que es más probable que las vistas de base de datos mantengan compatibilidad con versiones futuras de Lync Server.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de vista</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Vista ClientVersions en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los dispositivos o el software del cliente utilizados en una sesión de comunicación.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Vista ConferenceMessageCount en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre la cantidad de mensajes enviada por usuarios en una conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Vista de conferencias en Lync Server 2013</a></p></td>
<td><p>Devuelve información de conferencia, como por ejemplo la hora de inicio, la hora de finalización y el organizador de la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Vista ConferenceSessionDetails en Lync Server 2013</a></p></td>
<td><p>Devuelve información detallada de sesión de todas las sesiones de conferencia, como por ejemplo la hora de inicio y de finalización, los identificadores de usuarios, los códigos de respuesta y los identificadores de diagnóstico.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Vista ConferenceUris en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre URI de conferencias utilizados en una conferencia</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Vista ErrorReport en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los errores que se produjeron durante una sesión.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Vista FileTransfers en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre las sesiones de transferencia de archivos, incluido el nombre del archivo y si la transferencia fue aceptada, rechazada o cancelada.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Vista FocusJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre las actividades de conexión y desconexión de las conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Vista McuJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Devuelve información combinada sobre las actividades de conexión y desconexión de las conferencias (cada conexión a la conferencia se encuentra junto con la desconexión de la conferencia correspondiente).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Vista MCU en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre servidores de conferencias.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Vista de elementos multimedia en Lync Server 2013</a></p></td>
<td><p>Devuelve información acerca de los tipos de medios utilizados en las sesiones de comunicación punto a punto.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Vista ProgressReport en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre sesiones completadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Vista de registro en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los registros con Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Vista SessionDetails en Lync Server 2013</a></p></td>
<td><p>Returns information sobre sesiones punto a punto, incluidas las llamadas telefónicas VoIP-VoIP, las sesiones de mensajería instantánea entre dos participantes u otras sesiones de comunicación punto a punto.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Vista de usuario en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los usuarios que han participado en sesiones de comunicación.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Vista VoIPDetails en Lync Server 2013</a></p></td>
<td><p>Devuelve información para las sesiones punto a punto en las que haya participado al menos un usuario VoIP (Voz sobre IP).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

