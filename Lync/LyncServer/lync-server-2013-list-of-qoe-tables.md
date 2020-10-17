---
title: 'Lync Server 2013: lista de tablas de QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c5078ac2e8e97364455d88d32c79a03c58f0c2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513837"
---
# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Lista de tablas de QoE en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

El esquema de la base de datos incluye las tablas siguientes.

**Tablas auxiliares**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Tabla AppSharingMetricsThreshold en Lync Server 2013</a></p></td>
<td><p>Almacena los valores aceptables y óptimos para la métrica Calidad de la experiencia que se usa al compartir aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Tabla CodecDescription en Lync Server 2013</a></p></td>
<td><p>Asigna identificadores de códecs únicos al códec correspondiente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a></p></td>
<td><p>Asigna direcciones IP a los identificadores de dirección IP únicos que se usan en la base de datos de Calidad de la experiencia.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Tabla NetworkConnectionDetail en Lync Server 2013</a></p></td>
<td><p>Asigna tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de Calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Tabla PurgeSettings (QoE) en Lync Server 2013</a></p></td>
<td><p>Almacena información que especifica si los registros de Calidad de la experiencia no actualizados se eliminarán automáticamente de la base de datos de QoE (así como cuándo se eliminarán).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">TraceRoute tabla en Lync Server 2013</a></p></td>
<td><p>Almacena la información de enrutamiento de las llamadas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a></p></td>
<td><p>Asigna los identificadores de agente de usuario a los nombres descriptivos del agente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Tabla VideoMetricsThreshold en Lync Server 2013</a></p></td>
<td><p>Almacena los valores aceptables y óptimos para la métrica Calidad de la experiencia que se usa con las llamadas de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a></p></td>
<td><p>Almacena las cadenas del agente de usuario del Protocolo de inicio de sesión (SIP) y los tipos de agentes de usuario utilizados en las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Tabla user en Lync Server 2013</a></p></td>
<td><p>Almacena los URI de teléfono, usuario y conferencia utilizados en las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a></p></td>
<td><p>Almacena los nombres de equipo FQDN de los extremos que participan en las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Tabla de grupo en Lync Server 2013</a></p></td>
<td><p>Almacena los nombres de los grupos de servidores a los que pertenecen los datos de métricas.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a></p></td>
<td><p>Almacena los dispositivos de captura y presentación utilizados en las llamadas de audio/vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a></p></td>
<td><p>Almacena el controlador de los dispositivos de captura y presentación utilizados en las llamadas de audio/vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Tabla de conferencia en Lync Server 2013</a></p></td>
<td><p>Almacena los URI de conferencia para los escenarios de conferencia o el identificador de diálogo para otros escenarios.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Tabla SessionCorrelation en Lync Server 2013</a></p></td>
<td><p>Almacena el identificador de correlación de las llamadas RTC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Tabla PayloadDescription en Lync Server 2013</a></p></td>
<td><p>Almacena el códec utilizado en las llamadas de audio/vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Tabla AppliedBandwidthSource en Lync Server 2013</a></p></td>
<td><p>Almacena el origen de ancho de banda utilizado en las llamadas de audio/vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a></p></td>
<td><p>Almacena la dirección MAC de los extremos que participan en las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Tabla de cuadro de diálogo en Lync Server 2013</a></p></td>
<td><p>Almacena el identificador de diálogo de las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Tabla region en Lync Server 2013</a></p></td>
<td><p>Almacena la región de red definida en la configuración NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Tabla UserSite en Lync Server 2013</a></p></td>
<td><p>Almacena el sitio de red definido en la configuración NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Tabla de subred en Lync Server 2013</a></p></td>
<td><p>Almacena la subred definida en la configuración NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Tabla MonitoredRegionLink en Lync Server 2013</a></p></td>
<td><p>Almacena el vínculo de región definido en la configuración NCS.</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">Tabla MonitoredUserSiteLink</a></p></td>
<td><p>Almacena los vínculos de sitios de red definidos en la configuración NCS.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Tabla EndpointSubnet en Lync Server 2013</a></p></td>
<td><p>Almacena la subred del extremo que participa en las sesiones de audio y vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Tabla Server en Lync Server 2013</a></p></td>
<td><p>Almacena el FQDN o la dirección IP del servidor que utilizan los medios.</p></td>
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
<th><strong>Table</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Tabla AppSharingStream en Lync Server 2013</a></p></td>
<td><p>Almacena las métricas de Calidad de la experiencia para los flujos de red usados al compartir aplicaciones. Las métricas de calidad de la experiencia se usan al compartir aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Tabla Session en Lync Server 2013</a></p></td>
<td><p>Almacena información general acerca de una sesión de audio o de audio/vídeo. Una sesión se define como un diálogo SIP de audio o vídeo entre dos extremos.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a></p></td>
<td><p>Almacena información acerca de cada línea de medios de una sesión. Una línea de medios es una recopilación de una o varias secuencias de audio y vídeo. Por lo general, una única línea de medios tendrá dos secuencias, de audio o de vídeo.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Tabla AudioStream en Lync Server 2013</a></p></td>
<td><p>Almacena métricas de calidad de medios de audio para cada secuencia de audio de la línea de medios.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Tabla AudioSignal en Lync Server 2013</a></p></td>
<td><p>Almacena métricas de calidad de medios de audio de la línea de medios. Esto incluye las métricas de cancelación del eco acústico (AEC) y el control de ganancia automático (AGC).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Tabla Videostream en Lync Server 2013</a></p></td>
<td><p>Almacena métricas de calidad de medios de vídeo para cada secuencia de vídeo de la línea de medios.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Tabla AudioClientEvent en Lync Server 2013</a></p></td>
<td><p>Almacena métricas de calidad de medios de audio recopiladas desde el evento del cliente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Tabla VideoClientEvent en Lync Server 2013</a></p></td>
<td><p>Almacena métricas de calidad de medios de vídeo recopiladas desde el evento del cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla DiagnosticData</strong></p></td>
<td><p>Almacena datos de diagnóstico para uso interno únicamente.</p></td>
</tr>
</tbody>
</table>


**Tablas para datos de resumen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Descripción</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Tabla ServerSummary</strong></p></td>
<td><p>Almacena datos de resumen para los servidores; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla UserSummary</strong></p></td>
<td><p>Almacena datos de resumen para los usuarios; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla CallTypeSummary</strong></p></td>
<td><p>Almacena datos de resumen para los tipos de llamada; estos datos se usan para los informes QoE (Calidad de la experiencia) únicamente.</p></td>
</tr>
</tbody>
</table>


**Tablas para uso interno del servidor de supervisión**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Table</strong></th>
<th><strong>Descripción</strong></th>
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
<td><p><strong>Tabla FrontEnd</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla Task</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla CallSummary</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabla DeviceCallSumary</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabla Tenant</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>Únicamente para uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

