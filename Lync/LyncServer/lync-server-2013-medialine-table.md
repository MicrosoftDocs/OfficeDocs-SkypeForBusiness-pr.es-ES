---
title: 'Lync Server 2013: tabla MediaLine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03f967b50c2fa9eae4f2599ce96dc9c592a57006
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516147"
---
# <a name="medialine-table-in-lync-server-2013"></a>Tabla MediaLine en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-21_

Cada registro representa una línea de medios. (Una sesión de audio suele contener una línea de medios de audio. Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión puede contener dos líneas de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.


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
<td><p>Principal</p></td>
<td><p>Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>entero</p></td>
<td><p>Principal</p></td>
<td><p>Se hace referencia a ella desde la <a href="lync-server-2013-session-table.md">tabla Session en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>0 es el audio principal, 1 es el vídeo principal y 2 es vídeo panorámico, 3 es uso compartido de aplicaciones y escritorio. Esta etiqueta debe ser única en una sola sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Esta columna está presente pero no se usa en Microsoft Lync Server 2013. La información acerca de la conectividad usada para una línea de medios se captura en las columnas CallerConnectivityICE y CalleeConnectivityICE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>entero</p></td>
<td><p> </p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) que se describe en indicadores de bits. Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>entero</p></td>
<td><p> </p></td>
<td><p>Igual que CallerIceWarningFlags, pero en el lado del destinatario de la llamada. Para obtener más información, consulte la <em>especificación de protocolo de servidor de supervisión de calidad de la experiencia</em>, disponible para su descarga.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Seguridad</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 es UDP, 1 es TCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del autor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>entero</p></td>
<td><p> </p></td>
<td><p>Puerto del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>entero</p></td>
<td><p> Externa</p></td>
<td><p>La subred del autor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección Mac del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del servicio perimetral A/V de Lync Server que usa el autor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>entero</p></td>
<td><p> </p></td>
<td><p>Puerto usado en el servicio perimetral A/V por parte del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dispositivo de captura usado por el autor de la llamada. Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dispositivo de representación usado por el autor de la llamada. Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de captura del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de representación del autor de la llamada, a la que se hace referencia desde la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externa</p></td>
<td><p>Indica cómo el autor de la llamada se conectó a la red. Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>. Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>BSSID del autor de la llamada si se usa la tecnología inalámbrica. Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Vínculo del autor de la llamada. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal (18; 0)</p></td>
<td></td>
<td><p>Velocidad del vínculo de red, en bps, del extremo del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del receptor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Puerto usado por el receptor de llamadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Subred del destinatario de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que el receptor de la llamada se encuentra dentro de la red de la empresa, 0 significa que el receptor de la llamada está fuera de la red.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección Mac del destinatario de la llamada. Se hace referencia a ella desde la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el receptor de llamadas. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>entero</p></td>
<td><p> </p></td>
<td><p>Puerto usado en el servicio perimetral A/V por parte del receptor de llamadas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>entero</p></td>
<td><p>externa</p></td>
<td><p>Dispositivo de captura usado por el receptor de llamadas. Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dispositivo de representación usado por el receptor de llamadas. Se hace referencia a ella desde la <a href="lync-server-2013-device-table.md">tabla Device en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de captura del destinatario de la llamada. Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Externa</p></td>
<td><p>Controlador del dispositivo de representación del receptor de llamadas. Referencia de la <a href="lync-server-2013-devicedriver-table.md">tabla DeviceDriver en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externa</p></td>
<td><p>Indica cómo el destinatario de la llamada se conectó a la red. Los valores se obtienen de la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a>. Los valores típicos son 0 para una conexión cableada "1" para una conexión WiFi; y 3 para una conexión Ethernet.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>BSSID del destinatario de la llamada si se usa la tecnología inalámbrica. Referencia de la <a href="lync-server-2013-macaddress-table.md">tabla MacAddress en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Vínculo del receptor de llamadas; 1 es una red privada virtual (VPN), 0 no es VPN.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal (18; 0)</p></td>
<td><p> </p></td>
<td><p>Velocidad del vínculo de red, en bps, del extremo del receptor de llamadas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>entero</p></td>
<td></td>
<td><p>Este es el ancho de banda real que se aplica a la transmisión de la parte de envío determinada dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>Origen del límite de ancho de banda impuesto. Describe dónde procede el límite de ancho de banda ("Policy Server", "TURN Server", "Modate", etc.). Referencia de la <a href="lync-server-2013-appliedbandwidthsource-table.md">tabla AppliedBandwidthSource en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica si se recibieron las métricas del autor de la llamada; 1 es sí, un valor NULL es no.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Destinatario</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Indica si se recibieron las métricas del receptor de llamadas; 1 es sí, un valor NULL es no.</p></td>
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
<td><p>Indica si una llamada se ha clasificado como una llamada deficiente (valor 1) o como una buena llamada (0).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP reflexiva del usuario que realizó la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Descripción del dispositivo del controlador WiFi empleado por el usuario que realizó la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Número de versión del controlador WiFi empleado por el usuario que realizó la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Dirección IP reflexiva del usuario que recibió la llamada. En las organizaciones que usan NAT (traducción de direcciones de red), la dirección IP reflexiva es la dirección IP del servidor proxy.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
<td><p>Descripción del dispositivo del controlador WiFi empleado por el usuario que recibió la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>entero</p></td>
<td><p>Externa</p></td>
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

