---
title: 'Lync Server 2013: Tabla AudioClientEvent'
TOCTitle: Tabla AudioClientEvent
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48277297
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla AudioClientEvent en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro contiene un evento de cliente para un extremo de una llamada de audio. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llama.


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
<td><p>Se obtiene de <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Se obtiene de <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Principal</p></td>
<td><p>0: Datos del destinatario de la llamada</p>
<p>1: Datos del autor de la llamada</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento NetworkSendQuality para un estado no válido.</p>
<p>La calidad de red en cuanto a vibración o pérdida de paquetes es baja y afecta a la calidad del audio que se envía.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento ReceiveSendQuality para un estado no válido.</p>
<p>La calidad de red en cuanto a vibración o pérdida de paquetes es baja y afecta a la calidad del audio que se recibe.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento de retraso para un estado no válido. La latencia de red es grave y afecta a la experiencia evitando la comunicación interactiva</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento LowBandwidth para un estado no válido. No hay suficiente ancho de banda para tener una experiencia de voz aceptable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento de CPU insuficiente para un estado no válido. No hay suficientes ciclos de CPU para procesar con las modalidades y aplicaciones actuales en uso. Esto provoca distorsiones con el canal de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceHalfDuplexAEC para un estado no válido. Para evitar el eco, el sistema debe entrar en el modo de dúplex medio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceRenderNotFunctioning para un estado no válido. El dispositivo de presentación utilizado actualmente para la sesión no funciona correctamente. Esto puede provocar problemas de audio unidireccional.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceCaptureNotFunctioning para un estado no válido. El dispositivo de captura utilizado actualmente para la sesión no funciona correctamente. Esto puede provocar problemas de audio unidireccional.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceGlitches para un estado no válido. Hay varios problemas en la presentación de audio que provocan distorsiones. Estos problemas pueden deberse a errores de controladores, tormentas DPC (llamada a procedimiento diferido) (controladores) y un uso intensivo de la CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceLowSNR para un estado no válido. La calidad de captura es muy baja, ya sea porque hay mucho ruido o porque el usuario habla demasiado lejos del micrófono. Esto provocará distorsiones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceLowSpeechLevel para un estado no válido. El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo más. Esto puede provocar distorsiones o puede que se perciba como audio unidireccional.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceClipping para un estado no válido.</p>
<p>Cuando la voz del extremo cercano recorte el micrófono, en el otro extremo se oirán distorsiones debidas al recorte. Es importante evitar los recortes de micrófono del extremo cercano.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceEchoEvent para un estado no válido. El dispositivo o la configuración provocan un eco que el sistema no puede compensar.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceNearEndToEchoRatio para un estado no válido. El nivel de voz del usuario es demasiado bajo en comparación con el eco capturado, lo que afecta la experiencia del usuario porque limita la facilidad de interrumpir al usuario. Reduzca el volumen del altavoz, acerque el micrófono a la persona que habla.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Ocasiones durante la sesión en las que se desencadenó el evento DeviceMultipleEndpoints para un estado no válido. Se detectaron varios extremos de audio en la misma sesión y el sistema lo compensó reduciendo el volumen de presentación.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Ocasiones durante la sesión en las que se desencadenó el evento DeviceHowlingEvent para un estado no válido. Se ha detectado un bucle de retroalimentación de audio (provocado por varios extremos que comparten una ruta de audio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceRenderZeroVolume para un estado no válido.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Porcentaje de sesión por el que se desencadenó el evento DeviceRenderMute para un estado no válido.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

