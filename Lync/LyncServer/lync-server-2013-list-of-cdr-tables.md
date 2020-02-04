---
title: 'Lync Server 2013: Lista de tablas de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lista de tablas de CDR en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

El esquema de la base de datos de grabación de detalles de llamadas (CDR) consta de las siguientes tablas.

<div>

## <a name="static-tables"></a>Tablas estáticas


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
<td><p><a href="lync-server-2013-callpriorities-table.md">Tabla CallPriorities en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de posibles prioridades de llamadas, como emergencia, urgente, normal, no urgentes, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</a></p></td>
<td><p>Almacena los límites de clasificación usados por el informe de Resumen de tiempo de combinación de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Tabla DeRegisterType en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de posibles razones de anulación del registro de usuarios &quot;, como el&quot; &quot;cliente iniciado, el&quot; &quot;registro expirado&quot; , el bloqueo del cliente y mucho más.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Tabla MediaList en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Tabla PurgeSettings en Lync Server 2013</a></p></td>
<td><p>Almacena información que especifica si (y cuándo) los registros de detalles de llamadas obsoletas se eliminarán automáticamente de la base de datos de CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Tabla Roles en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de posibles roles de conferencia (por ejemplo, asistente y moderador).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Tabla SIPResponseMetaData en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de códigos de respuesta SIP, así como la clasificación y definición de cada uno de esos códigos.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Tablas de soporte técnico


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
<td><p><a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a></p></td>
<td><p>Almacena los clientes (tanto el tipo de cliente como el número de versión) de cada cliente implicado en una llamada con información capturada en esta base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de ConferenceURIs que se usan en llamadas relacionadas con la Conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Tabla ContentTypes en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de tipos de contenido de protocolo de inicio de sesión (SIP) que se usan en las llamadas de punto a punto y en las llamadas en conferencia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Tabla Devices en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de dispositivos, incluidos el fabricante, la versión de hardware y la dirección MAC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Tabla Dialogs en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre el identificador de cuadro de diálogo para cada sesión de la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de servidores perimetrales que se usan para llamadas externas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Tabla Gateways en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de puertas de enlace que se usan para llamadas de protocolo de voz a través de Internet (VoIP).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Tabla HardwareVersions en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de versiones de hardware de los dispositivos (teléfono de escritorio).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Tabla Manufacturers en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de fabricantes de dispositivos (teléfono de escritorio).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Tabla Mcus en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los diversos servidores de conferencia A/V y sus URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de servidores de mediación que se usan para llamadas de VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Tabla Phones en Lync Server 2013</a></p></td>
<td><p>Almacena todos los números de teléfono usados en llamadas VoIP que fueron archivados o cuyos detalles de llamadas fueron grabados.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Tabla Pools en Lync Server 2013</a></p></td>
<td><p>Almacena los nombres del grupo en el que se capturan los mensajes INSTANTÁNEos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a></p></td>
<td><p>Almacena el nombre de los servidores implicados en las llamadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a></p></td>
<td><p>Almacena los espacios empresariales admitidos por la implementación actual. Hay algunos inquilinos de compilación para usuarios de empresa, usuarios federados, usuarios de la conectividad de mensajería instantánea pública y usuarios anónimos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a></p></td>
<td><p>Asigna identificadores de agente de usuario a los nombres descriptivos del agente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Tabla Users en Lync Server 2013</a></p></td>
<td><p>Almacena los URI de usuario de los usuarios que participaron en sesiones grabadas o archivadas en esta base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Tabla UserStatistics en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre el uso del sistema por un usuario individual.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Tablas específicas de registros de CDR de conferencia


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
<td><p><a href="lync-server-2013-conferences-table.md">Tabla Conferences en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre todas las conferencias que se archivaron o cuyos detalles se grabaron, incluyendo ConferenceURI, y la hora de inicio y finalización.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Tabla ConferenceSessionDetails en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre todas las sesiones de conferencia basadas en SIP, como la hora de inicio y finalización, el identificador de usuario, el código de respuesta y el identificador de diagnóstico de cada sesión.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabla FocusJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de las uniones y las hojas de reuniones, incluidos el rol de los usuarios y la versión del cliente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabla McuJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre los servidores de conferencia A/V implicados en una conferencia y la combinación de usuarios y horas de salida.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Tablas de mensajes en conferencias de mensajería instantánea


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
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Tabla ConferenceMessageCount en Lync Server 2013</a></p></td>
<td><p>Para cada Conferencia de mensajería instantánea, almacena el número de mensajes que envió cada usuario.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Tabla IMReportSummary en Lync Server 2013</a></p></td>
<td><p>Proporciona un informe general sobre las sesiones de mensajería instantánea mantenidas en una organización.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Tablas para sesiones de punto a punto


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
<td><p><a href="lync-server-2013-sessiondetails-table.md">Tabla SessionDetails en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre cada sesión de punto a punto, incluyendo la hora de inicio y finalización, el identificador de usuario, el código de respuesta y el recuento de mensajes de cada usuario.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Tabla FileTransfers en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre las sesiones de transferencia de archivos, incluidos el nombre de archivo y el resultado (aceptada, rechazada o cancelada).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Tabla Media en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre los diferentes tipos de medios implicados en sesiones de punto a punto.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Tabla de detalles de llamadas VoIP


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
<td><p><a href="lync-server-2013-voipdetails-table.md">Tabla VoipDetails en Lync Server 2013</a></p></td>
<td><p>Para cada llamada de VoIP/RTC de dos partes, almacena información sobre la llamada, como el identificador de teléfono del teléfono VoIP, la puerta de enlace usada y qué parte se desconectó. Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para las horas de inicio y finalización de la llamada y el código de respuesta.</p>
<div>

> [!NOTE]  
> Si una de las partes de una llamada es un usuario de VoIP o si un servidor de mediación participó en la llamada, se creará un registro en esta tabla. La información sobre las llamadas de VoIP o VoIP que no implica un teléfono de red telefónica conmutada (RTC) se captura en la <A href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Tabla de auditorías de llamadas de E9-1-1


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
<td><p><a href="lync-server-2013-locations-table.md">Tabla Locations en Lync Server 2013</a></p></td>
<td><p>Para cada llamada de emergencia, como una llamada mejorada de 9-1-1 (E9-1-1), almacena información sobre la ubicación de la llamada. Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para las horas de inicio y finalización de la llamada y el código de respuesta.</p>
<div>

> [!NOTE]  
> Esta tabla solo contiene el BLOB de ubicación para la llamada de E9-1-1. Hace referencia a la tabla SessionDetails para obtener información detallada sobre la llamada.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tablas para la solución de problemas


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
<td><p><a href="lync-server-2013-application-table.md">Tabla Application en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los distintos procesos de Lync Server 2013 que participan en el enrutamiento y en las conexiones.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Tabla CallType en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre los tipos de la llamada, como "audio", "mensajería instantánea", "audio y vídeo" y "uso compartido de aplicaciones".</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Tabla ErrorCategory en Lync Server 2013</a></p></td>
<td><p>Almacena el nombre descriptivo de cada clasificación de diagnóstico de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Tabla ErrorDef en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre los tipos de errores y sus definiciones.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre los errores que se han producido.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Tabla ProgressReport en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre los informes de progreso de varios pasos implicados en los procesos de 2013 de Lync Server.</p></td>
</tr>
</tbody>
</table>


Las tablas de la siguiente lista son utilizadas internamente por Lync Server. Los detalles no se describen en este documento.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Tablas para uso interno de Lync Server


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
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla de FrontEnd</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla MSMQProcessing</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla de sindicación</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla SyndicatorsTenantMap</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla de tareas</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

