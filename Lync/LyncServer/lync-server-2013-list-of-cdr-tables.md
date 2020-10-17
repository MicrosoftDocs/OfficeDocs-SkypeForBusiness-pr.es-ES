---
title: 'Lync Server 2013: lista de tablas de CDR'
description: 'Lync Server 2013: lista de tablas de CDR.'
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
ms.openlocfilehash: 21d0f683ffeb0f5f1cbba5db4c45d248aa14e8e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558706"
---
# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lista de tablas de CDR en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-18_

El esquema de la base de datos del registro detallado de llamadas (CDR) incluye las tablas siguientes.

<div>

## <a name="static-tables"></a>Tablas estáticas


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
<td><p><a href="lync-server-2013-callpriorities-table.md">Tabla CallPriorities en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de posibles prioridades de llamada, como emergencia, urgente, normal, no urgente, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabla ConferenceJoinTimeThresholds en Lync Server 2013</a></p></td>
<td><p>Almacena los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Tabla DeRegisterType en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de posibles motivos de anulación del registro de usuario, como el &quot; cliente iniciado, el &quot; &quot; registro expirado, el &quot; &quot; bloqueo del cliente &quot; y mucho más.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Tabla de MediaL en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de tipos de medios que pueden generar entradas en la base de datos (por ejemplo, mensajería instantánea, audio, vídeo y transferencia de archivos).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Tabla PurgeSettings en Lync Server 2013</a></p></td>
<td><p>Almacena información que especifica si los registros de detalles de llamadas no actualizados se eliminarán automáticamente de la base de datos de CDR (así como cuándo se eliminarán).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Tabla roles en Lync Server 2013</a></p></td>
<td><p>Almacena la lista de posibles roles de conferencia (por ejemplo, participante y moderador).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Tabla SIPResponseMetaData en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de códigos de respuesta SIP, así como una clasificación y una definición de cada uno de estos códigos.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Tablas auxiliares


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
<td><p><a href="lync-server-2013-clientversions-table.md">Tabla ClientVersions en Lync Server 2013</a></p></td>
<td><p>Almacena los clientes (tipo de cliente y número de versión) de cada cliente que participa de una llamada con información capturada en esta base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Tabla ConferenceUris en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de ConferenceURI utilizados en las llamadas de conferencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Tabla ContentTypes en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de tipos de contenido del Protocolo de inicio de sesión (SIP) utilizados en las llamadas punto a punto y las llamadas de conferencia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Tabla Devices en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de dispositivos, incluido el fabricante, la versión de hardware y la dirección MAC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Tabla de cuadros de diálogo en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca del identificador de diálogo de cada sesión de la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Tabla EdgeServers en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de servidores perimetrales utilizados para las llamadas externas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Tabla gateways en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de puertas de enlace utilizadas para las llamadas de voz sobre IP (VoIP).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Tabla HardwareVersions en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de versiones de hardware de dispositivos (teléfono de escritorio).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Tabla Manufacturers en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de fabricantes de dispositivos (teléfono de escritorio).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Tabla MCU en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los diferentes servidores de conferencia A/V y sus URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Tabla MediationServers en Lync Server 2013</a></p></td>
<td><p>Almacena una lista de servidores de mediación utilizados para las llamadas VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Tabla teléfonos en Lync Server 2013</a></p></td>
<td><p>Almacena todos los números de teléfono utilizados en las llamadas VoIP que se archivaron o cuyos detalles se registraron.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Tabla pools en Lync Server 2013</a></p></td>
<td><p>Almacena los nombres del grupo de servidores en el que se capturan los mensajes instantáneos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Tabla Servers en Lync Server 2013</a></p></td>
<td><p>Almacena el nombre de los servidores que participan en llamadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Tabla Tenants en Lync Server 2013</a></p></td>
<td><p>Almacena los inquilinos admitidos por la implementación actual. Existen inquilinos integrados para usuarios de empresa, federados, de conectividad de mensajería instantánea pública y anónimos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Tabla UserAgentDef en Lync Server 2013</a></p></td>
<td><p>Asigna los identificadores de agente de usuario a los nombres descriptivos del agente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Tabla users en Lync Server 2013</a></p></td>
<td><p>Almacena los URI de los usuarios que participaron de sesiones registradas o archivadas en esta base de datos.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Tabla UserStatistics en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre el uso del sistema de un usuario individual.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Tablas específicas de registros CDR de conferencias


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
<td><p><a href="lync-server-2013-conferences-table.md">Tabla conferencias en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de todas las conferencias que se archivaron o cuyos detalles se registraron, incluido el URI de conferencia, y la hora de inicio y de finalización.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Tabla ConferenceSessionDetails en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de cada sesión de conferencia basada en SIP, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el identificador de diagnóstico de cada sesión.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabla FocusJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los usuarios que se unen a conferencias y las abandonan, incluida la versión de cliente y el rol de los usuarios.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabla McuJoinsAndLeaves en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los servidores de conferencia A/V utilizados en una conferencia, y la hora de conexión y desconexión del usuario.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Tablas para mensajes de conferencias de mensajería instantánea


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
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Tabla ConferenceMessageCount en Lync Server 2013</a></p></td>
<td><p>Para cada conferencia de mensajería instantánea, almacena el número de mensajes enviados por cada usuario.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Tabla IMReportSummary en Lync Server 2013</a></p></td>
<td><p>Proporciona un informe general de las sesiones de mensajería instantánea llevadas a cabo en una organización.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Tablas para sesiones punto a punto


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
<td><p><a href="lync-server-2013-sessiondetails-table.md">Tabla SessionDetails en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de cada sesión punto a punto, incluida la hora de inicio y de finalización, el identificador de usuario, el código de respuesta y el recuento de mensajes de cada usuario.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Tabla FileTransfers en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de las sesiones de transferencia de archivos, incluido el nombre de archivo y el resultado (aceptado, rechazado o cancelado).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Tabla de medios en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los diferentes tipos de medios utilizados en las sesiones punto a punto.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Tabla para detalles de llamadas VoIP


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
<td><p><a href="lync-server-2013-voipdetails-table.md">Tabla VoipDetails en Lync Server 2013</a></p></td>
<td><p>Para cada llamada VoIP/RTC de dos participantes, almacena información acerca de la llamada, como el identificador del teléfono VoIP, la puerta de enlace utilizada y el participante que desconectó la llamada. Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para llamar a las horas de inicio y finalización y el código de respuesta.</p>
<div>

> [!NOTE]  
> Si un participante de la llamada es un usuario VoIP o si se utilizó un servidor de mediación en la llamada, se creará un registro en esta tabla. La información sobre las llamadas VoIP/VoIP que no implican un teléfono de red telefónica conmutada (RTC) se captura en la <A href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Tabla para auditoría de llamadas E9-1-1


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
<td><p><a href="lync-server-2013-locations-table.md">Tabla Locations in Lync Server 2013</a></p></td>
<td><p>Para cada llamada de emergencia, como una llamada Enhanced 9-1-1 (E9-1-1), almacena información acerca de la ubicación de la llamada. Hace referencia a la <a href="lync-server-2013-sessiondetails-table.md">tabla SessionDetails en Lync Server 2013</a> para llamar a las horas de inicio y finalización y el código de respuesta.</p>
<div>

> [!NOTE]  
> Esta tabla solamente contiene el objeto binario grande de la ubicación de la llamada E9-1-1. Remítase a la tabla SessionDetails para obtener información adicional sobre la llamada.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tablas para solución de problemas


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
<td><p><a href="lync-server-2013-application-table.md">Tabla de aplicaciones en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre varios procesos en Lync Server 2013 que participan en el enrutamiento y las conexiones.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Tabla CallType en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los tipos de llamada, como “audio”, “mensajería instantánea”, “audio y vídeo” y “uso compartido de aplicaciones”.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Tabla categoría en Lync Server 2013</a></p></td>
<td><p>Almacena el nombre descriptivo para cada clasificación de diagnóstico de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Tabla ErrorDef en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los tipos de errores y sus definiciones.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Tabla ErrorReport en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de los errores generados.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Tabla ProgressReport en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre los informes de progreso de varios pasos implicados en los procesos de Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Las tablas de la lista siguiente se usan internamente en Lync Server. Los detalles no se describen en este documento.

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
<th>Table</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla FrontEnd</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla MSMQProcessing</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla Syndicators</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla SyndicatorsTenantMap</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla Task</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

