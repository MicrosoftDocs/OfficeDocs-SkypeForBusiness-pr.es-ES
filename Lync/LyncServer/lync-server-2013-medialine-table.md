---
title: 'Lync Server 2013: Tabla MediaLine'
TOCTitle: Tabla MediaLine
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48275035
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla MediaLine en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa una línea de medios (una sesión de audio suele contener una línea de medios de audio. Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencia o la Vista Galería).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Columna</strong></th>
<th><strong>Tipo de datos</strong></th>
<th><strong>Clave o índice</strong></th>
<th><strong>Detalles</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>Datetime</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-session-table.md">Tabla Session en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-session-table.md">Tabla Session en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>0 es audio principal, 1 es vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones/de escritorio. Esta etiqueta debe ser única en la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Esta columna se muestra, pero no se usa en Microsoft Lync Server 2013. La información sobre la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en marcas de bits. Si desea obtener información detallada, consulte la <em>Especificación del protocolo de servidor de supervisión de la calidad de la experiencia</em> , disponible para descarga.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Igual que CallerIceWarningFlags, pero con referencia a la persona que recibe la llamada. Si desea obtener información detallada, consulte la <em>Especificación del protocolo de servidor de supervisión de la calidad de la experiencia</em> , disponible para descarga.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Seguridad</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Perfil de seguridad que se está usando. 0 es NINGUNO, 1 es SRTP, 2 es V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transporte</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 es UDP, 1 es TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del autor de la llamada. Para más información, vea <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Puerto del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Subred de la llamada. Para más información, vea <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que el autor de la llamada se encuentra dentro de la red de la empresa, 0 significa que se encuentra fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección MAC del autor de la llamada; se obtiene de la <a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del servicio perimetral A/V de Lync Server que usa el destinatario de la llamada. Para más información, vea <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Puerto usado en el servicio perimetral A/V por parte del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dispositivo de captura empleado por el autor de la llamada. Se obtiene de <a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dispositivo de presentación que utiliza el autor de la llamada. Se obtiene de <a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de captura del autor de la llamada; se obtiene de <a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de presentación del autor de la llamada; se obtiene de <a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externa</p></td>
<td><p>Indica cómo se ha conectado el autor de la llamada a la red. Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">Tabla NetworkConnectionDetail en Lync Server 2013</a>. Los valores típicos son 0 para conexiones por cable, 1 para conexiones por Wi-Fi y 3 para conexiones Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>BSSID del autor de la llamada si se usa conexión inalámbrica. Se obtiene de la <a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Vínculo del autor de la llamada. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal(18,0)</p></td>
<td><p></p></td>
<td><p>Velocidad del vínculo de red, en bps, del extremo del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del destinatario de la llamada. Para más información, vea <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Puerto que usa el destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Subred del destinatario de la llamada. Para más información, vea <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que el destinatario de la llamada se encuentra dentro de la red de la empresa, 0 significa que se encuentra fuera de la red.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección MAC del destinatario de la llamada. Se obtiene de la <a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el receptor de la llamada. Para más información, vea <a href="lync-server-2013-ipaddress-table.md">Tabla IPAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Puerto usado en el servicio perimetral A/V por parte del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Externo</p></td>
<td><p>Dispositivo de captura empleado por el destinatario de la llamada. Se obtiene de <a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dispositivo de presentación empleado por el destinatario de la llamada. Se obtiene de <a href="lync-server-2013-device-table.md">Tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de captura del destinatario de la llamada. Se obtiene de <a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de presentación del destinatario de la llamada. Se obtiene de <a href="lync-server-2013-devicedriver-table.md">Tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externa</p></td>
<td><p>Indica cómo se ha conectado el destinatario de la llamada a la red. Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">Tabla NetworkConnectionDetail en Lync Server 2013</a>. Los valores típicos son 0 para conexiones por cable, 1 para conexiones por Wi-Fi y 3 para conexiones Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>BSSID del destinatario de la llamada si se usa conexión inalámbrica. Se obtiene de la <a href="lync-server-2013-macaddress-table.md">Tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Vínculo del destinatario de la llamada. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal(18,0)</p></td>
<td><p> </p></td>
<td><p>Velocidad del vínculo de red, en bps, del extremo del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal(3,2)</p></td>
<td><p> </p></td>
<td><p>MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Este es el ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Este es el origen del límite de ancho de banda que se está imponiendo. Indica de dónde procede el límite de ancho de banda (“Servidor de directivas”, “Servidor TURN”, “Modalidad”, etc.). Se obtiene de <a href="lync-server-2013-appliedbandwidthsource-table.md">Tabla AppliedBandwidthSource en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Autor de la llamada</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica si se han recibido las métricas del autor de la llamada: 1 significa que sí y un valor nulo, que no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica si se han recibido las métricas del destinatario de la llamada: 1 significa que sí y un valor nulo, que no.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si el informe es una parte de la sesión o de la sesión completa.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indica si una llamada se clasificó como una llamada deficiente (valor 1) o como una buena llamada (0).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td><p></p></td>
<td><p>Indica si el autor de la llamada se conectó a la red usando el protocolo ICE (Establecimiento de conectividad de Internet).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>Indica si el autor de la llamada se conectó a la red usando el protocolo ICE (Establecimiento de conectividad de Internet).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP reflexiva del usuario que realizó la llamada. En organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Descripción del dispositivo del controlador Wi-Fi utilizado por el usuario que realizó la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número de versión del controlador Wi-Fi utilizado por el usuario que realizó la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP reflexiva del usuario que recibió la llamada. En organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Descripción del dispositivo del controlador Wi-Fi utilizado por el usuario que recibió la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>Int</p></td>
<td><p>Externa</p></td>
<td><p>Número de versión del controlador Wi-Fi utilizado por el usuario que recibió la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

