---
title: 'Lync Server 2013: tabla AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f0d37de40340a66e6d87365ce40924f6c6d98f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Tabla AudioClientEvent en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Cada registro contiene un evento de cliente para un punto de conexión en una llamada de audio. Normalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario de la llamada.


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
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Referencia de la <a href="lync-server-2013-medialine-table.md">tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Principal</p></td>
<td><p>0: datos del destinatario de la llamada</p>
<p>1: datos del autor de la llamada</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento NetworkSendQuality para un estado "incorrecto".</p>
<p>La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento ReceiveSendQuality para un estado "incorrecto".</p>
<p>La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento Delay se activó para el estado "Bad". La latencia de red es grave y afecta a la experiencia al evitar la comunicación interactiva</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento LowBandwidth para un estado "incorrecto". El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión el evento de CPU insuficiente se activó para el estado "incorrecto". No hay ciclos de CPU suficientes para el procesamiento con las aplicaciones actuales y las aplicaciones en uso. Esto causa distorsiones con el canal de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceHalfDuplexAEC para un estado "incorrecto". Para evitar el eco, el sistema tiene que tener un dúplex medio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceRenderNotFunctioning para un estado "incorrecto". El dispositivo de representación que se está usando actualmente para la sesión no funciona correctamente. Esto puede provocar problemas de audio en una dirección.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceCaptureNotFunctioning para un estado "incorrecto". El dispositivo de captura que se está usando actualmente para la sesión no funciona correctamente. Esto puede provocar problemas de audio en una dirección.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceGlitches para un estado "incorrecto". Hay problemas graves en la representación del audio que está causando distorsiones. Estos problemas pueden deberse a problemas de controladores, a las llamadas de procedimiento diferido (DPC) y al uso intensivo de la CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceLowSNR para un estado "incorrecto". La calidad de la captura es muy mala, ya sea muy ruidosa o el usuario está hablando demasiado lejos del micrófono. Esto hará que se produzcan distorsiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceLowSpeechLevel para un estado "incorrecto". El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo más. Esto puede causar distorsiones o percibirse como un audio unidireccional.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceClipping para un estado "incorrecto".</p>
<p>Cuando la voz próxima a la vez recorta el micrófono, la distorsión del extremo final oirá una distorsión debido al recorte. Es importante evitar el recorte de micrófono cerca de la finalización.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento resaltó un evento para un estado "incorrecto". El dispositivo o el programa de instalación está causando eco más allá de la capacidad del sistema para compensar.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión en la que se activó el evento DeviceNearEndToEchoRatio para un estado "incorrecto". La voz del usuario es demasiado baja en comparación con el eco que se está capturando y que afecta a la experiencia de los usuarios, ya que limita lo fácil que resulta interrumpir a un usuario. Reduce el volumen del altavoz, mueve el micrófono más cerca del Talker.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de veces durante la sesión en que se activó el evento DeviceMultipleEndpoints para un estado "incorrecto". Se han detectado varios puntos de conexión de audio en la misma sesión y el sistema ha compensado mediante la reducción del volumen de representación.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Número de veces durante la sesión en que se activó el evento DeviceHowlingEvent para un estado "incorrecto". Bucle de comentarios de audio detectado (causado por varios puntos de conexión que comparten la ruta de audio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>Porcentaje de sesión en la que se ha desencadenado el evento DeviceRenderZeroVolume para estar en el estado "incorrecto". El dispositivo de representación se estableció en un volumen de cero.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>Porcentaje de sesión en la que se ha desencadenado el evento DeviceRenderMute para estar en el estado "incorrecto". El dispositivo de representación está silenciado.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

