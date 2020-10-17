---
title: 'Lync Server 2013: vista de MediaLine'
description: 'Lync Server 2013: vista de MediaLine.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c61fcc15b46958622e6cddd66427255a6def154
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568686"
---
# <a name="medialine-view-in-lync-server-2013"></a>Vista MediaLine en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La vista MediaLine almacena información acerca de cada línea de medios de la base de datos. Una sesión de audio normalmente contiene una línea de medios de audio. Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería. Esta vista se introdujo en Microsoft Lync Server 2013.


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
<th>details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>entero</p></td>
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>entero</p></td>
<td><p>Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>entero</p></td>
<td><p>Información acerca del proceso de establecimiento interactivo de conectividad (ICE), proceso descrito en indicadores de bits para el destinatario de la llamada. Para obtener detalles, consulte el protocolo de servidor de supervisión de calidad de experiencia.</p></td>
</tr>
<tr class="even">
<td><p>Seguridad</p></td>
<td><p>tinyint</p></td>
<td><p>Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de transporte. 0 es UDP, 1 es TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del autor de la llamada. Esta puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>entero</p></td>
<td><p>Puerto del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada está o no dentro de la red la organización. 1 significa que el autor de la llamada se encuentra dentro de la red de empresa. 0 significa que el autor de la llamada se encuentra fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Dirección MAC de la interfaz de red usada por el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>entero</p></td>
<td><p>Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del autor de llamada según la notifica el servicio perimetral A/V. Esta dirección puede ser diferente de CallerIPAddr si el cliente se encuentra detrás de una NAT por ejemplo.</p></td>
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
<td><p>CallerRenderDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre de controlador de dispositivo de presentación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>VARCHAR (256</p></td>
<td><p>Descripción del controlador Wifi del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Versión del controlador Wifi del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Detalles de la conexión de red del autor de la llamada. Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Identificador de conjunto de servicio básico usado por conexión WiFi de autores de llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de llamada se conectó a través de una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del destinatario de la llamada. Esta puede ser una dirección IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>entero</p></td>
<td><p>Puerto del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>Indica si el autor de la llamada se encuentra dentro de la red de empresa. 1 significa el destinatario de la llamada dentro de la red de empresa, 0 significa el destinatario de la llamada fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Dirección MAC de la interfaz de red usada por el destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V usado por el autor de la llamada. Consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>entero</p></td>
<td><p>Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del destinatario de llamada según lo notifica el servicio perimetral A/V. Esta dirección puede ser diferente de CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
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
<td><p>Nombre de controlador de dispositivo de presentación del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Descripción del controlador Wifi del destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>VARCHAR (256</p></td>
<td><p>Versión del controlador Wifi del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Detalles de la conexión de red del destinatario de la llamada. Consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> para obtener más información.</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Identificador de conjunto de servicio básico usado por la conexión WiFi del destinatario de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada se conectó por una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>entero</p></td>
<td><p>Este es el ancho de banda real aplicado a la secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Origen del límite de ancho de banda impuesto. Describe de dónde proviene el límite de ancho de banda (por ejemplo, “Servidor de directivas”, “Servidor TURN” o “Modalidad”).</p></td>
</tr>
<tr class="odd">
<td><p>Caller</p></td>
<td><p>bit</p></td>
<td><p>Indica si se han recibido las métricas del autor de la llamada. 1 indica que sí, 0 que no.</p></td>
</tr>
<tr class="even">
<td><p>Destinatario</p></td>
<td><p>bit</p></td>
<td><p>Indica si se han recibido las métricas del destinatario de la llamada. 1 indica que sí, 0 que no.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>Indica si el informe es para una parte de la llamada o para la llamada completa.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>Indica si una llamada se clasificó como deficiente (1) o como llamada correcta (0).</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el usuario llamado se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE)</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

