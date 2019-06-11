---
title: 'Lync Server 2013: lista de vistas de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112e565c07c685c1ecdf5db1d8a2de8717ba959e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lista de vistas de CDR en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Las vistas proporcionan una forma fácil de obtener acceso a la información sobre los escenarios más comunes que se usan para devolver datos de la base de datos de CDR. Se recomienda usar vistas para crear informes personalizados en lugar de usar las tablas de base de datos de CDR reales; Esto se debe a que las vistas de la base de datos tienen más probabilidades de mantener la compatibilidad con versiones futuras de Lync Server.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de la vista</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Vista ClientVersions en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre el software de cliente o los dispositivos que se usan en una sesión de comunicación.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Vista ConferenceMessageCount en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre el número de mensajes enviados por los usuarios en una conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Vista conferencias en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre la Conferencia, como la hora de inicio, la hora de finalización y el organizador de la Conferencia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Vista ConferenceSessionDetails en Lync Server 2013</a></p></td>
<td><p>Devuelve detalles de sesión para todas las sesiones de conferencia, como la hora de inicio y finalización, los identificadores de usuario, los códigos de respuesta y los identificadores de diagnóstico.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Vista ConferenceUris en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre las URI de conferencia que se usan en una conferencia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Vista ErrorReport en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los errores que se produjeron durante una sesión.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Vista FileTransfers en Lync Server 2013</a></p></td>
<td><p>Devuelve información acerca de las sesiones de transferencia de archivos, incluido el nombre de archivo y si la transferencia fue aceptada, rechazada o cancelada.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Vista FocusJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Devuelve información acerca de las actividades unirse a la Conferencia y abandonar.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Vista McuJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Devuelve información combinada sobre las actividades de unirse a la Conferencia y abandonar (cada unión de conferencia se empareja con la salida correspondiente de la Conferencia).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Vista MCU en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los servidores de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Vista de elementos multimedia de Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los tipos de elementos multimedia usados en sesiones de comunicación de punto a punto.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Vista ProgressReport en Lync Server 2013</a></p></td>
<td><p>Devuelve información acerca de las sesiones completadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Vista de registro en Lync Server 2013</a></p></td>
<td><p>Devuelve información acerca de los registros con Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Vista SessionDetails en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre sesiones de punto a punto, como llamadas telefónicas VoIP-VoIP, sesiones de mensajería instantánea de dos participantes u otras sesiones de comunicación punto a punto.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Vista de usuario en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre los usuarios que participaron en sesiones de comunicación.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Vista VoIPDetails en Lync Server 2013</a></p></td>
<td><p>Devuelve información sobre sesiones de punto a punto con al menos un usuario de VoIP (voz sobre IO).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

