---
title: 'Lync Server 2013: Tabla MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Tabla MediaLine en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-21_

Cada registro representa una línea de medios. (Una sesión de audio normalmente contiene una línea multimedia de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo, aunque la sesión podría contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.


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
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-session-table.md">tabla sesión en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-session-table.md">tabla sesión en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>0 es el audio principal, 1 es el vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones y escritorio. Esta etiqueta debe ser única dentro de una sola sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Esta columna está presente pero no se usa en Microsoft Lync Server 2013. La información sobre la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits. Para obtener más información, consulte la <em>especificación de protocolo de servidor calidad de la supervisión</em>, disponible para descargar.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada. Para obtener más información, consulte la <em>especificación de protocolo de servidor calidad de la supervisión</em>, disponible para descargar.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Seguridad</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Perfil de seguridad en uso. 0 es ninguno, 1 es SRTP, 2 es v1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 es UDP, 1 es TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección IP del autor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Puerto usado por el autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> Extranjero</p></td>
<td><p>La subred de la persona que llama. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección Mac de la persona que llama, a la que se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección IP del servicio perimetral de Lync Server A/V que usa el autor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Puerto usado en el servicio de borde de A/V por el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dispositivo de captura usado por el autor de la llamada. Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dispositivo de representación usado por la persona que llama. Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Controlador para el dispositivo de captura de la persona que llama, al que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Controlador del dispositivo de representación de la persona que llama, al que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Extranjero</p></td>
<td><p>Indica cómo se conectó a la red. Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>. Los valores típicos son 0 para una conexión cableada ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>BSSID del autor de la llamada si se usa una conexión inalámbrica. Se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Vínculo de la persona que llama. 1 es una red privada virtual (VPN) y 0 no es una VPN.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal (18; 0)</p></td>
<td></td>
<td><p>La velocidad del vínculo de red, en bps, para el punto final de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección IP del receptor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puerto usado por el receptor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Subred del destinatario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que el receptor de llamadas está dentro de la red empresarial, 0 significa que el receptor de la llamada está fuera de la red.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección Mac de la llamada. Se hace referencia a ellos desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el receptor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Puerto usado en el servicio de borde A/V por el receptor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>extranjero</p></td>
<td><p>Dispositivo de captura usado por el receptor de la llamada. Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dispositivo de representación usado por el receptor de la llamada. Se hace referencia a ellos desde la <a href="lync-server-2013-device-table.md">tabla de dispositivos en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Controlador para el dispositivo de captura del receptor de la llamada. Se hace referencia a partir de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Extranjero</p></td>
<td><p>Controlador del dispositivo de representación del receptor de la llamada. Se hace referencia a partir de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Extranjero</p></td>
<td><p>Indica cómo el destinatario de la llamada está conectado a la red. Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>. Los valores típicos son 0 para una conexión cableada ' 1 para una conexión WiFi; y 3 para una conexión Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>BSSID del destinatario de la llamada si se usa la tecnología inalámbrica. Se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Vínculo del receptor de la llamada; 1 es una red privada virtual (VPN) y 0 no es una VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal (18; 0)</p></td>
<td><p> </p></td>
<td><p>La velocidad del vínculo de red, en bps, para el extremo del receptor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Este es el ancho de banda real aplicado a la transmisión de la parte de envío proporcionada, que proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Este es el origen del límite de ancho de banda que se impone. Describe dónde viene el límite de ancho de banda ("servidor de directivas", "TURN Server", "Modación", etc.). Se hace referencia a ellos desde la <a href="lync-server-2013-appliedbandwidthsource-table.md">tabla AppliedBandwidthSource en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Autor de llamada</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica si se recibieron las métricas de la persona que llama; 1 es sí, un valor nulo es no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario de la llamada</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica si se han recibido métricas del receptor de la llamada; 1 es sí, un valor nulo es no.</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica si el informe es para una parte de la sesión o para la sesión completa.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica si una llamada se ha clasificado como una llamada deficiente (valor de 1) o como una buena llamada (0).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección IP reflexiva del usuario que realizó la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Descripción del dispositivo para el controlador WiFi empleado por el usuario que realizó la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Número de versión del controlador WiFi empleado por el usuario que realizó la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Dirección IP reflexiva del usuario que recibió la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Descripción del dispositivo para el controlador WiFi empleado por el usuario que recibió la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>Número de versión del controlador WiFi empleado por el usuario que recibió la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

