---
title: 'Lync Server 2013: vista AudioStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Vista AudioStreamDetail en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La vista AudioStreamDetail almacena información acerca de cada secuencia de audio de la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.


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
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>IDENTIFICADOR exclusivo dentro de una línea de medios.</p></td>
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
<td><p>Categoría de cuadro de diálogo: 0 es el servidor de Lync para el servidor de mediación; 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Marcador que indica si la llamada se ha omitido o no.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Si está presente, indica por qué no se omitió una llamada aunque los identificadores de omisión coincidan. Solo se define un valor:</p>
<p>0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</p></td>
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
<td><p>Tipo del agente de usuario de la llamada. Para obtener más información, vea la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> .</p></td>
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
<td><p>Número de núcleos de CPU en el extremo de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos de la CPU en el punto final de la llamada.</p></td>
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
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Clave de correlación. Se hace referencia a ellos desde la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Información sobre la ruta multimedia, como Direct o retransmitida. Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de transporte: 0 es UDP, 1 es TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado por el autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si la persona que llama está dentro de la red de intervalos: 1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del destinatario. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado por el destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada está dentro de la red de intervalos: 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del sitio de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del país o de la región del sitio de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del sitio de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del país o región del sitio de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado en el servicio de borde A/V que usa el destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de representación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de representación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de captura de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de representación de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de representación de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si la persona que llama se conecta a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es una VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal (18; 0)</p></td>
<td><p>Velocidad de vínculo de red para el punto final de la llamada en bps.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si la persona que llama se conecta a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es una VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal (18; 0)</p></td>
<td><p>Velocidad de vínculo de red para el punto final de la persona que llama en bps.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>El ancho de banda real aplicado a la transmisión de la parte de envío dada proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Vibración máxima de la red durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Tasa promedio de pérdida de paquetes durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Pérdida máxima de paquetes observadas durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Densidad promedio de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Densidad media de pérdida de paquetes entre ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Duración media de los huecos entre las ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Recuento de paquetes de la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>Ancho de banda más</p></td>
<td><p>int</p></td>
<td><p>Cálculo de ancho de banda para la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Degradación de MOS de red para toda la llamada. El intervalo está comprendido entre 0,0 y 5,0. Esta métrica muestra el monto que se redujo en el MOS de red debido a la vibración y a la pérdida de paquetes. Para una calidad aceptable, debe ser menor que 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>La degradación de OP máxima de red durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Degradación de MOS de red causada por vibración.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Degradación de MOS de red causada por pérdida de paquetes.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>El códec de audio usado para la llamada, al que se hace referencia desde la <a href="lync-server-2013-payloaddescription-table.md">tabla PayloadDescription en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Frecuencia de muestreo de la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel posterior de señal de audio de control de ganancia analógica para el audio enviado por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio del audio recibido por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>El nivel de ruido de audio de control de ganancia posterior analógico para el audio enviado por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>El nivel de ruido de audio de control de ganancia posterior analógico para el audio recibido por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Return echo Return Enhancement para la persona que llama. La unidad para esta métrica es dB. Los valores más bajos representan menos eco. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Promedio de problemas por cinco minutos para la representación del altavoz de la persona que llama. Para obtener una buena calidad, debe ser inferior a un período de 5 minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Promedio de problemas por cinco minutos para la captura de micrófono de la persona que llama. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de la persona que llama, en relación con el reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Velocidad de desplazamiento del reloj del dispositivo de altavoz del autor de la llamada, relativa al reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Promedio del error de marca de tiempo de la secuencia de representación de altavoces de la persona que llama, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causas de un evento de Eco para el autor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Porcentaje de tiempo en que se detecta eco en el flujo de captura de micrófono de la persona que llama. Si se usa un auricular, el valor debe ser bajo.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Porcentaje de tiempo durante el que se detecta eco en el flujo enviado de la persona que llama. Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser de-30 a-18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Control automático de ganancia (AGC) en el servidor de mediación aplicado al audio de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Cuadrado principal raíz (RMS) de la señal entrante al autor de la llamada durante los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Representa el nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio del audio recibido por el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>El nivel de ruido de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>El nivel de ruido de audio de control de ganancia posterior analógico para el audio recibido. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Return echo Return Enhancement para el destinatario de la llamada. La unidad para esta métrica es dB. Los valores más bajos representan menos eco. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Promedio de problemas por cinco minutos para la representación del altavoz de la persona que llama. Para obtener una buena calidad, debe ser inferior a un período de 5 minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Promedio de problemas por cinco minutos para la captura de micrófono de la persona que llama. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de micrófono del destinatario, relativa al reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de altavoz de la llamada, relativa al reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimal (9; 2)</p></td>
<td><p>Promedio del error de marca de tiempo del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causas de un evento de Eco para el destinatario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Porcentaje de tiempo durante el que se detecta eco en el flujo de captura de micrófono de la persona que llama. Si se usa un auricular, el valor debe ser bajo.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Porcentaje de tiempo durante el que se detecta eco en el flujo enviado de la persona que llama. Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser [-30 a-18] dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Control automático de ganancia (AGC) en el servidor de mediación aplicado al audio de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Cuadrado de la media raíz (RMS) de la señal entrante para el destinatario durante los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Relación media entre las muestras ocultas generadas por la corrección de audio a muestras típicas.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Relación media de muestras extendidas generadas por la recuperación de audio a muestras típicas.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal (4,5)</p></td>
<td><p>Relación media de muestras comprimidas generadas por la corrección de audio a muestras típicas.</p></td>
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
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>MOS de red de banda ancha promedio para la llamada. Esta métrica depende de la pérdida del paquete, de la vibración y del códec usado. El intervalo está comprendido entre 1,0 y 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>MOS de red de banda ancha mínima para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluyendo el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>SendListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluido el nivel de voz, nivel de ruido, códec, condiciones de red y características de dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>RecvListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>Indica si se usó el audio FEC para la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Indica la dirección de la información identificada por p; 1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada. 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

