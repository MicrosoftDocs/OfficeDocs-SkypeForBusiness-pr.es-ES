﻿---
title: Vista VideoStreamDetail
TOCTitle: Vista VideoStreamDetail
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49889799
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista VideoStreamDetail

 

_**Última modificación del tema:** 2015-03-09_

La vista VideoStreamDetail almacena información de todas las secuencias de vídeo en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<td><p>Referencia realizada desde la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Referencia realizada desde la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Referencia realizada desde la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>Identificador único de una línea de medios.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora de inicio de la sesión.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora de finalización de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Prioridad de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de autores de llamadas.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de destinatarios de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>Callee</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario del autor de la llamada. Consulte la <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Categoría de agente de usuario del autor de la llamada. Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena del agente de usuario del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario del destinatario de la llamada. Consulte la <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Categoría de agente de usuario del destinatario de la llamada. Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nombre del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Sistema operativo (SO) del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Sistema operativo (SO) del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre de la CPU del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre de la CPU del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos de CPU del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos de CPU del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocidad del procesador de la CPU del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocidad del procesador de la CPU del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el sistema del autor de la llamada se está ejecutando en un entorno visualizado. Consulte la <a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado. Consulte la <a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Información sobre la ruta de medios, como directa o retransmitida. Consulte la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>Tipo de transporte: 0 es UDP y 1 es TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Puerto del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Dirección IP del destinatario de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Puerto del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el destinatario de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del centro del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del país o región del centro del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del centro del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del país o la región del centro del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto en el servicio perimetral A/V que usa el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p>
<p></p></td>
<td><p>Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto en el servicio perimetral A/V que usa el destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de presentación del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador dispositivo de presentación del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de captura del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de presentación del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red del autor de la llamada: 0 es con cable y 1, inalámbrica.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal(18,)</p></td>
<td><p>Velocidad del vínculo de red del extremo del autor de la llamada en bps.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red del destinatario de la llamada: 0 es con cable y 1, inalámbrica.</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</p></td>
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
<td><p>Tiempo de ida y vuelta máximo de la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Promedio de frecuencia de pérdida de paquetes durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Pérdida máxima de paquetes observada durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>Previsiones de ancho de banda de la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Códec de audio utilizado por la llamada, obtenido de la <a href="lync-server-2013-payloaddescription-table.md">Tabla PayloadDescription en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char(9)</p></td>
<td><p>Resolución del vídeo en píxeles de ancho multiplicados por píxeles de alto. Se proporciona como cadena.</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>Tasa de bits media de la secuencia de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Tasa de fotogramas de vídeo recibida.</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Tasa de fotogramas de vídeo enviada.</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>Tasa de bits de vídeo máxima durante la sesión de vídeo.</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Tasa a la que se perdieron los paquetes de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>decimal(9.4)</p></td>
<td><p>Porcentaje del total de fotogramas de vídeo que se pierde.</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>bit</p></td>
<td><p>No se usa.</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>Cantidad máxima del ancho de banda asignada para vídeo.</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>decimal(9.4)</p></td>
<td><p>Porcentaje del total de fotogramas de vídeo que se perdió.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Dirección de secuencia de la información de identidad p-asserted. El valor 1 indica que la dirección de la secuencia es del autor de la llamada al destinatario; y 0 significa del destinatario al autor.</p></td>
</tr>
</tbody>
</table>

