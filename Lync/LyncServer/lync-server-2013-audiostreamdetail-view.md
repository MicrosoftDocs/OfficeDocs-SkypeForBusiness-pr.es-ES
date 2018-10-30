---
title: Vista AudioStreamDetail
TOCTitle: Vista AudioStreamDetail
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49889547
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vista AudioStreamDetail

 

_**Última modificación del tema:** 2015-03-09_

La vista AudioStreamDetail almacena información sobre cada secuencia de audio de la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>Se obtiene de la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Se obtiene de la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>Identificador único de una línea de medios.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Hora de inicio de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Hora de finalización de la sesión.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Categoría del cuadro de diálogo; 0 es la sección de Lync Server al servidor de mediación; 1 es la sección del servidor de mediación a la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Marca que indica si la llamada se pasó o no.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Si está presente, indica por qué la llamada no se pasó, incluso si los identificadores de omisión coincidían. Solo se define un valor:</p>
<p>0x0001: identificador de omisión desconocido del adaptador de red predeterminado.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Prioridad de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>FQDN del grupo de destinatario de la llamada.</p></td>
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
<td><p>Tipo de agente de usuario del autor de la llamada. Para más información, vea la <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Categoría del agente de usuario del autor de la llamada. Para más información, vea la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Cadena de agente de usuario del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario del destinatario de la llamada. Para más información, vea la <a href="lync-server-2013-useragent-table.md">Tabla UserAgent en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Categoría del agente de usuario del destinatario de la llamada. Para más información, vea la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabla UserAgentDef (QoE) en Lync Server 2013</a>.</p></td>
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
<td><p>Sistema operativo del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Sistema operativo del extremo del destinatario de la llamada.</p></td>
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
<td><p>Velocidad del procesador de CPU del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocidad del procesador de CPU del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el sistema del autor de la llamada se ejecuta en un entorno virtualizado. Para más información, vea la <a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el sistema del destinatario de la llamada se ejecuta en un entorno virtualizado. Para más información, vea la <a href="lync-server-2013-endpoint-table.md">Tabla Endpoint en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td><p></p></td>
<td><p>Clave de correlación. Se obtiene de la <a href="lync-server-2013-sessioncorrelation-table.md">Tabla SessionCorrelation en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Información sobre la ruta de medios, como directa o retransmitida. Para más información, vea la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en marcas de bits para el autor de la llamada. Para más información, vea la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en marcas de bits para el destinatario de la llamada. Para más información, vea la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de transporte: 0 es UDP, 1 es TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Puerto que usa el autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada está dentro de la red del intervalo: 1 significa que el autor de la llamada se encuentra dentro de la red de la empresa, 0 significa que se encuentra fuera de la red.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Dirección IP del destinatario de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Puerto que usa el destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada está dentro de la red del intervalo: 1 significa que el destinatario de la llamada se encuentra dentro de la red de la empresa, 0 significa que se encuentra fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del sitio del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del país o región del sitio del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del sitio del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>Nombre del país o región del sitio del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para más información, vea la <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto del servicio perimetral A/V que usa el autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Para más información, vea la <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto del servicio perimetral A/V que usa el destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de presentación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador del dispositivo de presentación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de captura del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del dispositivo de presentación del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red del autor de la llamada: 0 es cableada, 1 es inalámbrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada se conectó a través de una red privada virtual (VPN): 1 es VPN, 0 es diferente de VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>Velocidad del vínculo de red del extremo del autor de la llamada en bps.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red del destinatario de la llamada: 0 es cableada, 1 es inalámbrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada se conectó a través de una red privada virtual (VPN): 1 es VPN, 0 es diferente de VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Puntuación MOS de la conversación de banda estrecha de las sesiones de audio (basada en ambas secuencias de audio).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Vibración media de la red en las estadísticas del Protocolo de control en tiempo real (RTCP).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Vibración máxima de la red durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Frecuencia media de pérdida de paquetes durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>Pérdida máxima de paquetes observada durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Densidad media de pérdida de paquetes en las ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Duración media de pérdida de paquetes en las ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>Densidad media de pérdida de paquetes durante intervalos entre ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Duración media de intervalos entre ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Número de paquetes de la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>Previsiones de ancho de banda de la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Degradación MOS de red de toda la llamada. El intervalo va desde 0,0 hasta 5,0. Esta métrica muestra cuánto se redujo la MOS de red debido a la vibración y la pérdida de paquetes. Para que la calidad sea aceptable, debe ser menor que 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Degradación MOS máxima de red durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Degradación MOS de red provocada por la vibración.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Degradación MOS de red provocada por la pérdida de paquetes.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Códec de audio usado para la llamada, obtenido de la <a href="lync-server-2013-payloaddescription-table.md">Tabla PayloadDescription en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Frecuencia de muestreo de la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio del control de ganancia postanalógico para el audio que envió el autor de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser de al menos 30 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio para el audio que recibió el autor de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser de al menos 30 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de ruido de audio del control de ganancia postanalógico para el audio que envió el autor de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de ruido de audio del control de ganancia postanalógico para el audio que recibió el autor de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Mejora de la pérdida del retorno de eco para el autor de la llamada. La unidad de esta métrica es dB. Los valores inferiores representan un eco menor. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Número medio de problemas generados cada cinco minutos para la presentación del altavoz del autor de la llamada. Para que la calidad sea buena, debe ser inferior a uno cada cinco minutos. No se notifica en los servidores de conferencia A/V, los servidores de mediación ni los teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Número medio de problemas generados cada cinco minutos para la captura del micrófono del autor de la llamada. Para que la calidad sea buena, debe ser inferior a uno cada cinco minutos. No se notifica en los servidores de conferencia A/V, los servidores de mediación ni los teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Índice de desfase del reloj del dispositivo del micrófono del autor de la llamada, con respecto al reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Índice de desfase del reloj del dispositivo del altavoz del autor de la llamada, con respecto al reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Número medio de errores en marcas de tiempo de secuencia de captura del micrófono del autor de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Número medio de errores en marcas de tiempo de secuencia de presentación del altavoz del autor de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>La conmutación de voz es un modo de dúplex medio con capacidad de interrupción reducida. Para más información, vea la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causas de un evento de eco del autor de la llamada. Para más información, vea la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono del autor de la llamada. Si se usan auriculares, el valor debe ser bajo.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia de envío del autor de la llamada. Un porcentaje alto de eco en las secuencias de envío indica la presencia de filtraciones de eco.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de la señal recibida en el servidor de mediación desde la puerta de enlace para el audio del autor de la llamada. Solamente se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para que la calidad sea buena, el intervalo aceptable debe ser de -30 a -18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de la señal recibida en el servidor de mediación desde la puerta de enlace para el audio del autor de la llamada. Solamente se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para que la calidad sea buena, el intervalo aceptable debe ser inferior a -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Valor cuadrático medio (RMS) de la señal entrante del autor de la llamada correspondiente a los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio del control de ganancia postanalógico para el audio que envió el destinatario de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser de al menos 30 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio para el audio que recibió el destinatario de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser de al menos 30 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de ruido de audio del control de ganancia postanalógico para el audio que envió el destinatario de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de ruido de audio del control de ganancia postanalógico para el audio que recibió el destinatario de la llamada. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Mejora de la pérdida del retorno de eco para el destinatario de la llamada. La unidad de esta métrica es dB. Los valores inferiores representan un eco menor. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Número medio de problemas generados cada cinco minutos para la presentación del altavoz del destinatario de la llamada. Para que la calidad sea buena, debe ser inferior a uno cada cinco minutos. No se notifica en los servidores de conferencia A/V, los servidores de mediación ni los teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Número medio de problemas generados cada cinco minutos para la captura del micrófono del destinatario de la llamada. Para que la calidad sea buena, debe ser inferior a uno cada cinco minutos. No se notifica en los servidores de conferencia A/V, los servidores de mediación ni los teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Índice de desfase del reloj del dispositivo del micrófono del destinatario de la llamada, con respecto al reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Índice de desfase del reloj del dispositivo del altavoz del destinatario de la llamada, con respecto al reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Número medio de errores en marcas de tiempo de secuencia de captura del micrófono del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>Número medio de errores en marcas de tiempo de secuencia de presentación del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>La conmutación de voz es un modo de dúplex medio con capacidad de interrupción reducida. Para más información, vea la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causas de un evento de eco del destinatario de la llamada. Para más información, vea la <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono del destinatario de la llamada. Si se usan auriculares, el valor debe ser bajo.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia de envío del destinatario de la llamada. Un porcentaje alto de eco en las secuencias de envío indica la presencia de filtraciones de eco.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de la señal recibida en el servidor de mediación desde la puerta de enlace para el audio del destinatario de la llamada. Solamente se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para que la calidad sea buena, el intervalo aceptable debe ser de [-30 a -18] dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de la señal recibida en el servidor de mediación desde la puerta de enlace para el audio del destinatario de la llamada. Solamente se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para que la calidad sea buena, el intervalo aceptable debe ser inferior a -50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Valor cuadrático medio (RMS) de la señal entrante del destinatario de la llamada correspondiente a los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Relación media de muestras ocultas generadas por la recuperación de audio en muestras típicas.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Relación media de muestras extendidas generadas por la recuperación de audio en muestras típicas.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>Relación media de muestras comprimidas generadas por la recuperación de audio en muestras típicas.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Tiempo de ida y vuelta de las estadísticas de RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Tiempo de ida y vuelta máximo de la secuencia de vídeo.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>MOS media de red de banda ancha de la llamada. Esta métrica depende de la pérdida de paquetes, la vibración y el códec usado. El intervalo oscila entre 1,0 y 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>MOS mínima de red de banda ancha de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Predicción de puntuación media de MOS de escucha de banda ancha del audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Valor de SendListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Predicción de puntuación media de MOS de escucha de banda ancha del audio recibido a través de la red, incluido el nivel de voz, el nivel de ruido, el códec, las condiciones de red y las características del dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>Valor de RecvListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>Indica si se usó FEC de audio para la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Indica la dirección de la información de identificación p-asserted: 1 indica que la dirección de la secuencia va del autor al destinatario de la llamada; 0 indica que la dirección de la secuencia va del destinatario al autor de la llamada.</p></td>
</tr>
</tbody>
</table>

