---
title: 'Lync Server 2013: Tabla AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489777458838d5e77df1f8c82ed6ab8b6c295832
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Tabla AudioClientEvent en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Cada registro contiene un evento de cliente para un punto final en una llamada de audio. Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.


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
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>Se hace referencia a ellos desde la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Primary</p></td>
<td><p>0: datos del destinatario de la llamada</p>
<p>1: datos del autor de la llamada</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento NetworkSendQuality se activó por el estado "incorrecto".</p>
<p>La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento ReceiveSendQuality se activó por el estado "incorrecto".</p>
<p>La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta la calidad de audio que se recibe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de la sesión el evento de retraso se activó para el estado "incorrecto". La latencia de la red es grave y afecta a la experiencia al evitar la comunicación interactiva</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento LowBandwidth se activó por el estado "incorrecto". El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento de CPU insuficiente se activó para el estado "incorrecto". No hay suficientes ciclos de CPU para procesar con las aplicaciones y las aplicaciones actuales en uso. Esto causa distorsiones en el canal de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceHalfDuplexAEC se activó por el estado "incorrecto". Para evitar que se produzca el eco, el sistema se introduce a doble cara.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceRenderNotFunctioning se activó por el estado "incorrecto". El dispositivo de representación que se usa actualmente para la sesión no funciona correctamente. Esto puede dar lugar a problemas de audio unidireccionales.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceCaptureNotFunctioning se activó por el estado "incorrecto". El dispositivo de captura usado actualmente para la sesión no funciona correctamente. Esto puede dar lugar a problemas de audio unidireccionales.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceGlitches se activó por el estado "incorrecto". Hay problemas graves en la representación de audio que causan distorsiones. Estos problemas pueden estar causados por problemas de controlador, tormentas de llamadas a procedimiento diferidas (DPC) y uso intensivo de la CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceLowSNR se activó por el estado "incorrecto". La calidad de la captura es muy mala, ya sea muy ruidosa o el usuario habla demasiado lejos del micrófono. Esto provocará distorsiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceLowSpeechLevel se activó por el estado "incorrecto". El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo. Esto puede causar distorsiones o percibir como audio unidireccional.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceClipping se activó por el estado "incorrecto".</p>
<p>Cuando los recortes de voz próximos se recortan, el micrófono escucha la distorsión del extremo a causa de la recorte. Es importante evitar el recorte de micrófono cerca de la final.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceEchoEvent se activó por el estado "incorrecto". El dispositivo o el programa de instalación está causando eco más allá de la capacidad del sistema para compensar.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento DeviceNearEndToEchoRatio se activó por el estado "incorrecto". La voz del usuario es demasiado baja en comparación con el eco que se está capturando y que afecta a la experiencia de los usuarios porque limita lo fácil que es interrumpir a un usuario. Reduce el volumen del altavoz, mueve el micrófono cerca de la Talker.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de veces durante la sesión el evento DeviceMultipleEndpoints se activó por el estado "incorrecto". Se detectaron varios puntos de conexión de audio en la misma sesión y el sistema se ha compensado al reducir el volumen de representación.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Número de veces durante la sesión el evento DeviceHowlingEvent se activó por el estado "incorrecto". Se detectó un bucle de comentarios de audio (causado por varios puntos de conexión que comparten la ruta de audio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td></td>
<td><p>Porcentaje de sesión el evento DeviceRenderZeroVolume se activó por estar en el estado "incorrecto". El dispositivo de representación se estableció en un volumen de cero.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td></td>
<td><p>Porcentaje de sesión el evento DeviceRenderMute se activó por estar en el estado "incorrecto". El dispositivo de representación se ha silenciado.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

