---
title: 'Lync Server 2013: vista de AudioStreamDetail'
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
ms.openlocfilehash: fe995d08bf334308603512b4812b02c672d400f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Vista AudioStreamDetail en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

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
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>Identificador único de una línea de medios.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora de inicio de la sesión.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Fecha y hora de finalización de la sesión.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Categoría del cuadro de diálogo: 0 es el segmento del servidor de mediación de Lync. 1 es el servidor de mediación a la pierna de la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Marca que indica si la llamada se ha omitido o no.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Si está presente, indica por qué no se omitió una llamada incluso si coinciden los identificadores de omisión. Solo se define un valor:</p>
<p>0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Prioridad de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del grupo de autores de llamadas.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del grupo de destinatarios de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>Destinatario</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Cadena de agente de usuario del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario del autor de la llamada. Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría del agente de usuario del autor de la llamada. Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Cadena del agente de usuario del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo de agente de usuario del destinatario de la llamada. Consulte la <a href="lync-server-2013-useragent-table.md">tabla UserAgent en Lync Server 2013</a> para obtener información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoría de agente de usuario del destinatario de la llamada. Consulte la <a href="lync-server-2013-useragentdef-table-qoe.md">tabla UserAgentDef (QoE) en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nombre del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Sistema operativo (SO) del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Sistema operativo (SO) del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre de la CPU del extremo del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre de la CPU del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Número de núcleos de CPU en el extremo del autor de la llamada.</p></td>
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
<td><p>Indica si el sistema del autor de la llamada se está ejecutando en un entorno visualizado. Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado. Consulte la <a href="lync-server-2013-endpoint-table.md">tabla Endpoint en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Clave de correlación. Referencia de la <a href="lync-server-2013-sessioncorrelation-table.md">tabla SessionCorrelation en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Información sobre la ruta de medios, como directa o retransmitida. Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de transporte: 0 es UDP y 1 es TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Puerto del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada está dentro de la red del intervalo: 1 significa que el autor de la llamada está dentro de la red de la empresa, 0 significa que el autor de la llamada está fuera de la red.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del destinatario de la llamada. Puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Puerto del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada está dentro de la red del intervalo: 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del centro del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del país o región del centro del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del centro del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128</p></td>
<td><p>Nombre del país o la región del centro del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de presentación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador dispositivo de presentación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del dispositivo de captura del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre de dispositivo de presentación del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de captura del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de presentación del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red del autor de la llamada: 0 es con cable y 1, inalámbrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal (18; 0)</p></td>
<td><p>Velocidad del vínculo de red del extremo del autor de la llamada en bps.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de conexión de red del destinatario de la llamada: 0 es con cable y 1, inalámbrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal (18; 0)</p></td>
<td><p>Velocidad del vínculo de red del extremo del destinatario de la llamada en bps.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Vibración máxima de la red durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimal (5, 4)</p></td>
<td><p>Promedio de frecuencia de pérdida de paquetes durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal (5, 4)</p></td>
<td><p>Pérdida máxima de paquetes observada durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>Densidad</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Densidad media de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Duración media de la pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimal (9, 4)</p></td>
<td><p>Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Duración media de brechas entre ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Número de paquetes de la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>Ancho de banda más</p></td>
<td><p>int</p></td>
<td><p>Previsiones de ancho de banda de la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Degradación de MOS de red para toda la llamada. El intervalo es de 0,0 a 5,0. Esta métrica muestra la cantidad de MOS de red que se redujo debido a la vibración y pérdida de paquetes. Para una calidad aceptable, debe ser inferior a 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Degradación de MOS de red máxima durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Degradación de MOS de red causada por la vibración.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Degradación de MOS de red causada por la pérdida de paquetes.</p></td>
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
<td><p>Nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el autor de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio para el audio que el autor de la llamada ha recibido. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>El nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el autor de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>El nivel de ruido de audio del control de ganancia posterior analógico para el audio que ha recibido la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Devolución de pérdida eco mejora para el autor de la llamada. La unidad para esta métrica es dB. Los valores inferiores representan menos eco. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media de problemas por cinco minutos para la representación del altavoz del autor de la llamada. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media de problemas por cinco minutos para la captura del micrófono del autor de la llamada. Para una buena calidad, debe ser inferior a uno por cinco minutos. No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de micrófono del autor de la llamada en relación con el reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de altavoz del autor de la llamada en relación con el reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Promedio del error de marca de tiempo de la secuencia de representación del altavoz del autor de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causas de un evento de Eco para el autor de la llamada. Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal (5, 2)</p></td>
<td><p>Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del autor de la llamada. Si se usa el casco, el valor debería ser bajo.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal (5, 2)</p></td>
<td><p>Porcentaje de tiempo en que se detecta el eco en la secuencia enviada del autor de la llamada. Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el intervalo aceptable debe ser de-30 a-18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del autor de la llamada. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Cuadrado raíz medio (RMS) de la señal entrante al autor de la llamada durante los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Representa el nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal de audio para el audio que el destinatario de la llamada ha recibido. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de ruido de audio del control de ganancia posterior analógico para el audio que envió el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de ruido de audio del control de ganancia posterior analógico para el audio que el destinatario de la llamada ha recibido. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Devolución de pérdida de Eco para el destinatario de la llamada. La unidad para esta métrica es dB. Los valores inferiores representan menos eco. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media de problemas por cinco minutos para la representación del altavoz del destinatario de la llamada. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media de problemas por cinco minutos para la captura del micrófono del destinatario de la llamada. Para una buena calidad, debe ser inferior a uno por cinco minutos. No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de micrófono del destinatario de la llamada en relación con el reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de altavoz del destinatario de la llamada en relación con el reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimal (9, 2)</p></td>
<td><p>Promedio del error de marca de tiempo de la secuencia de representación del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Causas de un evento echo para el destinatario de la llamada. Consulte la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal (5, 2)</p></td>
<td><p>Porcentaje de tiempo en que se detecta el eco en la secuencia de captura del micrófono del destinatario de la llamada. Si se usa el casco, el valor debería ser bajo.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal (5, 2)</p></td>
<td><p>Porcentaje de tiempo en que se detecta eco en la secuencia enviada del destinatario de la llamada. Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Control de ganancia automático (AGC) en el servidor de mediación aplicado al audio del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>Cuadrado raíz medio (RMS) de la señal entrante al destinatario de la llamada durante los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal (5, 2)</p></td>
<td><p>Relación media de muestras ocultas generadas por la recuperación de audio en muestras típicas.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal (5, 2)</p></td>
<td><p>Relación media de muestras extendidas generadas por la recuperación de audio en muestras típicas.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal (5, 2)</p></td>
<td><p>Relación media de muestras comprimidas generadas por la recuperación de audio en muestras típicas.</p></td>
</tr>
<tr class="even">
<td><p>Vuelta</p></td>
<td><p>int</p></td>
<td><p>Tiempo de ida y vuelta de las estadísticas de RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Tiempo de ida y vuelta máximo de la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>MOS de red de banda ancha promedio para la llamada. Esta métrica depende de la pérdida de paquetes, la vibración y el códec que se usan. El intervalo es de 1,0 a 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>MOS de red de banda ancha mínima para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>SendListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>Puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y la captura de las características del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>RecvListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>Indica si se usó el FEC de audio para la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>Indica la dirección de la información de identificación p-asserted; 1 significa que la dirección de la secuencia proviene del autor de la llamada al destinatario de la llamada; 0 significa que la dirección de la secuencia es del destinatario de la llamada al autor de la llamada.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

