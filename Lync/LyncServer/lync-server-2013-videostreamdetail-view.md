---
title: 'Lync Server 2013: vista VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Vista VideoStreamDetail en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La vista VideoStreamDetail almacena información acerca de cada secuencia de vídeo de la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.


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
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR exclusivo dentro de una línea de medios.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Hora de inicio de la sesión.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Prioridad de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de llamadas.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de destinatarios de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>Autor de llamada</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>Destinatario de la llamada</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario de la llamada. Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario del destinatario de la llamada. Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario del destinatario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del punto de conexión de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del extremo de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Sistema operativo (SO) del punto final de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Sistema operativo (SO) del extremo de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre de la CPU del punto final de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre de la CPU del punto final de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos de CPU del punto final de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos de CPU del punto final de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocidad del procesador de CPU del punto final de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocidad del procesador de CPU del punto final de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado. Para obtener más información, consulte la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado. Para obtener más información, consulte la <a href="lync-server-2013-endpoint-table.md">tabla de extremos en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Información sobre la ruta multimedia, como Direct o retransmitida. Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>Tipo de transporte: 0 es UDP, 1 es TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado por el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si la persona que llama está dentro de la red de la organización. 1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del destinatario. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado por el destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si la persona que llama está dentro de la red de la organización. 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del sitio de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del país o de la región del sitio de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del sitio de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del país o región del sitio de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto en el servicio perimetral A/V usado por el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto del servicio perimetral A/V usado por el destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de representación del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de representación del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de captura de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de representación de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de representación de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada se ha conectado a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal (18;)</p></td>
<td><p>Velocidad de vínculo de red para el punto final de la llamada en bps.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada se conecta a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal (18; 0)</p></td>
<td><p>Velocidad de vínculo de red del extremo de la persona que llama (en bps).</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>El ancho de banda real aplicado a la transmisión de la parte de envío dada proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Vibración máxima de la red durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Tiempo de ida y vuelta de las estadísticas de RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Tiempo máximo de ida y vuelta para la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Tasa promedio de pérdida de paquetes durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Pérdida máxima de paquetes observadas durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</p></td>
</tr>
<tr class="odd">
<td><p>Ancho de banda más</p></td>
<td><p>int</p></td>
<td><p>Cálculo de ancho de banda para la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Códec de audio usado para la llamada, al que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Resolución de la</p></td>
<td><p>carácter (9)</p></td>
<td><p>Resolución del vídeo en píxeles ancho multiplicado por píxeles alto. Se ha notificado como una cadena.</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>Promedio de velocidad de bits de la secuencia de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Velocidad de fotogramas de video recibido.</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Velocidad de fotogramas enviada.</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>Máxima tasa de bits de vídeo durante la sesión de video.</p></td>
</tr>
<tr class="even">
<td><p>Tasa</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Velocidad a la que se han perdido paquetes de video.</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>decimal (9.4)</p></td>
<td><p>Porcentaje de fotogramas de video totales que se pierden.</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>bit</p></td>
<td><p>No usado.</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>Cantidad promedio de ancho de banda asignado para el vídeo.</p></td>
</tr>
<tr class="even">
<td><p>Media</p></td>
<td><p>decimal (9.4)</p></td>
<td><p>Porcentaje de fotogramas de video totales que se han perdido.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Dirección de la secuencia para la información de identidad declarada en p. 1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada. 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

