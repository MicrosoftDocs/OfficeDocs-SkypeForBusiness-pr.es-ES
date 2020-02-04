---
title: 'Lync Server 2013: vista MediaLine'
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
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Vista MediaLine en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

La vista MediaLine almacena información acerca de cada línea de medios de la base de datos. Una sesión de audio normalmente contiene una línea multimedia de audio. Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo; sin embargo, la sesión podría contener dos líneas multimedia de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería. Esta vista se presentó en Microsoft Lync Server 2013.


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
<th>sobre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
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
<td><p>Seguridad</p></td>
<td><p>tinyint</p></td>
<td><p>Perfil de seguridad en uso. 0 es ninguno, 1 es SRTP, 2 es v1.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo de transporte. 0 es UDP, 1 es TCP.</p></td>
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
<td><p>Indica si el autor de la llamada está dentro de la red de la organización. 1 significa que la persona que llama está dentro de la red empresarial. 0 significa que la persona que llama está fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Dirección MAC de la interfaz de red que llama.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP de la persona que llama según el servicio perimetral de A/V. Esta dirección puede ser diferente de la CallerIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</p></td>
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
<td><p>CallerRenderDevDriver</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Nombre del controlador del dispositivo de representación del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>VARCHAR (256</p></td>
<td><p>Descripción del controlador WIFI del autor de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Versión del controlador WIFI del autor de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Detalles de la conexión de red de la persona que llama. Para obtener más información, consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Identificador del conjunto de servicios básicos usado por las personas que llaman conexión WiFi.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si la persona que llama se ha conectado a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.</p></td>
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
<td><p>Indica si el destinatario de la llamada está dentro de la red empresarial. 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Dirección MAC de la interfaz de red que usa el destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Para obtener más información, consulte la <a href="lync-server-2013-ipaddress-table.md">tabla IPAddress en Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Puerto usado en el servicio de borde A/V que usa el destinatario de la llamada.</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Dirección IP del destinatario de la llamada tal y como lo indica el servicio A/V Edge. Esta dirección puede ser diferente de la CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var (50)</p></td>
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
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Descripción del controlador WIFI de la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>VARCHAR (256</p></td>
<td><p>Versión del controlador WIFI de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Detalles de la conexión de red de la persona que llama. Para obtener más información, consulte la <a href="lync-server-2013-networkconnectiondetail-table.md">tabla NetworkConnectionDetail en Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Identificador del conjunto de servicios básicos usado por la conexión WiFi de la persona que llama.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>Indica si el destinatario de la llamada se conecta a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal (3, 2)</p></td>
<td><p>OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Este es el ancho de banda real que se aplica a la transmisión de la parte de envío proporcionada, dadas varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no debe confundirse con el ancho de banda efectivo porque puede haber un ancho de banda más bajo en función de la estimación del ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>VARCHAR (256)</p></td>
<td><p>Origen del límite de ancho de banda que se impone. Describe de dónde viene el límite de ancho de banda (por ejemplo, "servidor de directivas", "convertir servidor" o "modalidad de moda").</p></td>
</tr>
<tr class="odd">
<td><p>Autor de llamada</p></td>
<td><p>bit</p></td>
<td><p>Indica si se recibieron las métricas de la persona que llama; 1 es sí, 0 es no.</p></td>
</tr>
<tr class="even">
<td><p>Destinatario de la llamada</p></td>
<td><p>bit</p></td>
<td><p>Indica si se han recibido métricas del receptor de la llamada; 1 es sí, 0 es no.</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>Indica si el informe es para una parte de la llamada o para la llamada completa.</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>Indica si una llamada se ha clasificado como una llamada deficiente (1) o como una buena llamada (0).</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si la persona que llama se ha conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>Indica si el usuario ha sido llamado conectado a la red mediante el protocolo ICE (establecimiento de conectividad de Internet).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

