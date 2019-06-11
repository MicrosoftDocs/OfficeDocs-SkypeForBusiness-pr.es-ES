---
title: 'Lync Server 2013: Lista de tablas de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c82c38a995fd9e847057fedbbce1422085332b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Lista de tablas de QoE en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

El esquema de la base de datos consta de las siguientes tablas.

**Tablas de soporte técnico**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabla</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabla AppSharingMetricsThreshold en Lync Server 2013</a></p></td>
<td><p>Almacena valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con el uso compartido de aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Tabla CodecDescription en Lync Server 2013</a></p></td>
<td><p>Asigna identificadores de códec únicos a su códec correspondiente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a></p></td>
<td><p>Asigna direcciones IP a los identificadores de dirección IP única que se usan en otras partes de la base de datos de la calidad de la experiencia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Tabla NetworkConnectionDetail en Lync Server 2013</a></p></td>
<td><p>Mapas tipos de conexión de red a los identificadores de conexión de red usados en otras partes de la base de datos de la calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Tabla PurgeSettings (QoE) en Lync Server 2013</a></p></td>
<td><p>Almacena información que especifica si (y cuándo) la calidad de los registros de experiencia se eliminará automáticamente de la base de datos de QoE.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Tabla TraceRoute en Lync Server 2013</a></p></td>
<td><p>Almacena la información de enrutamiento de las llamadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a></p></td>
<td><p>Asigna identificadores de agente de usuario a los nombres descriptivos del agente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Tabla VideoMetricsThreshold en Lync Server 2013</a></p></td>
<td><p>Almacena valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con las videollamadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a></p></td>
<td><p>Almacena las cadenas y los tipos de UA del agente de usuario del Protocolo de inicio de sesión (SIP) que se usan en sesiones de audio y vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Tabla User en Lync Server 2013</a></p></td>
<td><p>Almacena los URI de usuario, Conferencia y teléfono que se usan en las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a></p></td>
<td><p>Almacena FQDN de los nombres de los equipos de puntos de conexión que participan en sesiones de audio y vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Tabla Pool en Lync Server 2013</a></p></td>
<td><p>Almacena los nombres de los grupos a los que pertenecen los datos de métrica.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a></p></td>
<td><p>Almacena dispositivos de captura y dispositivos de representación que se usan en una llamada de audio o vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a></p></td>
<td><p>Almacena el controlador para el dispositivo de captura y el dispositivo de representación que se usan en las llamadas de audio o vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Tabla Conference en Lync Server 2013</a></p></td>
<td><p>Almacena los URI de conferencia para escenarios de conferencia o DialogID para otros escenarios.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Tabla SessionCorrelation en Lync Server 2013</a></p></td>
<td><p>Almacena CorrelationID para llamadas RTC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Tabla PayloadDescription en Lync Server 2013</a></p></td>
<td><p>Almacena el códec usado en las llamadas de audio o vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabla AppliedBandwidthSource en Lync Server 2013</a></p></td>
<td><p>Almacena la fuente de ancho de banda que se usa en las llamadas de audio o vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a></p></td>
<td><p>Almacena la dirección MAC de los puntos de conexión que participan en sesiones de audio y vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Tabla Dialog en Lync Server 2013</a></p></td>
<td><p>Almacena el identificador de cuadro de diálogo de las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Tabla Region en Lync Server 2013</a></p></td>
<td><p>Almacena la región de red definida en NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Tabla UserSite en Lync Server 2013</a></p></td>
<td><p>Almacena el sitio de red definido en NC Settings.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Tabla Subnet en Lync Server 2013</a></p></td>
<td><p>Almacena la subred definida en la configuración de NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Tabla MonitoredRegionLink en Lync Server 2013</a></p></td>
<td><p>Almacena el vínculo región definido en NC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Tabla MonitoredUserSiteLink</a></p></td>
<td><p>Almacena los vínculos de sitio de red definidos en NC.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Tabla EndpointSubnet en Lync Server 2013</a></p></td>
<td><p>Almacena la subred del punto final que participa en una sesión de audio y vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Tabla Server en Lync Server 2013</a></p></td>
<td><p>Almacena el FQDN o la dirección IP del servidor en el que se recorren los medios.</p></td>
</tr>
</tbody>
</table>


**Tablas para datos de métricas**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabla</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Tabla AppSharingStream en Lync Server 2013</a></p></td>
<td><p>Almacena métricas de experiencia de evaluación de la calidad de las secuencias de red usadas para compartir aplicaciones. Métricas de la calidad de la experiencia de las secuencias de red que se usan para compartir aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Tabla Session en Lync Server 2013</a></p></td>
<td><p>Almacena información general sobre una sesión de audio o vídeo o audio. Una sesión se define como un cuadro de diálogo SIP de audio o vídeo entre dos puntos finales.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a></p></td>
<td><p>Almacena información sobre cada línea multimedia de una sesión. Una línea de medios es una colección de una o más secuencias de audio y vídeo. Normalmente, una única línea multimedia tendrá dos secuencias, ya sea audio o vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Tabla AudioStream en Lync Server 2013</a></p></td>
<td><p>Almacena las métricas de calidad de audio multimedia de audio de cada flujo de audio de la línea de medios.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Tabla AudioSignal en Lync Server 2013</a></p></td>
<td><p>Almacena las métricas de calidad de audio multimedia en la línea media. Esto incluye la métrica de cancelación de eco acústico (AEC) y las métricas de control automático de ganancia (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Tabla VideoStream en Lync Server 2013</a></p></td>
<td><p>Almacena métricas de calidad de medios de vídeo para cada flujo de audio de la línea de medios.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Tabla AudioClientEvent en Lync Server 2013</a></p></td>
<td><p>Almacena las métricas de calidad de audio multimedia recopiladas del evento de cliente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Tabla VideoClientEvent en Lync Server 2013</a></p></td>
<td><p>Almacena las métricas de calidad de medios de vídeo recopiladas desde el evento de cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla DiagnosticData</strong></p></td>
<td><p>Almacena datos de diagnóstico que solo son para uso interno.</p></td>
</tr>
</tbody>
</table>


**Tablas de datos de Resumen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabla</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tabla ServerSummary</strong></p></td>
<td><p>Almacena los datos de Resumen de los servidores, estos datos se usan únicamente para los informes de calidad de la experiencia (QoE).</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla UserSummary</strong></p></td>
<td><p>Almacena los datos de Resumen de los usuarios, estos datos se usan solo para informes de QoE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla CallTypeSummary</strong></p></td>
<td><p>Almacenar datos de Resumen de tipos de llamadas: estos datos se usan para informes de QoE únicamente.</p></td>
</tr>
</tbody>
</table>


**Tablas para uso interno mediante el servidor de supervisión**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Tabla</strong></th>
<th><strong>Descripción</strong></th>
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
<td><p><strong>Tabla de FrontEnd</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla de tareas</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla CallSummary</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla DeviceCallSumary</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla de inquilinos</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Solo para uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

