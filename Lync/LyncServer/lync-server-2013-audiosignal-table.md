---
title: 'Lync Server 2013: Tabla AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Tabla AudioSignal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-12_

Cada registro representa las métricas de señal de audio de un extremo. Normalmente, cada llamada tiene dos registros, uno para la persona que llama y el otro es para el destinatario de la llamada.


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Representa el nivel de señal de audio de control de ganancia posterior analógico. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consulta SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Representa el nivel de ruido de audio del control de ganancia posterior analógico. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consulta SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Métrica de mejora de pérdida de eco. La unidad para esta métrica es dB. Los valores más bajos representan menos eco. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Promedio de problemas por cinco minutos para el procesamiento de altavoz. Para obtener una buena calidad, debe ser inferior a un período de 5 minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Promedio de problemas por cinco minutos para la captura del micrófono. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>Velocidad de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>Velocidad de desplazamiento del reloj del dispositivo de altavoz, relativa al reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>Velocidad de desplazamiento del reloj del dispositivo de altavoz, relativa al reloj de la CPU.</p>
<p>Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal (9; 2)</p></td>
<td><p> </p></td>
<td><p>El altavoz promedio representa el error de marca de tiempo de la secuencia, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Causas de la entrada de conmutación de voz:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>La causa puede ser una combinación de estas causas individuales. La clave de permiso solo puede habilitarse ENTER_VS_FORCEORCONVERGENCE para fines de prueba.</p>
<p>El tipo de datos de esta columna se modificó en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Causas de un evento de eco:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>La causa puede ser una combinación de estas causas individuales.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td></td>
<td><p>Porcentaje de tiempo durante el que se detecta eco en el flujo enviado. Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser [-30 a-18] dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Control automático de ganancia (AGC) en el servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>El cuadrado de la media raíz (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de señal como recibido en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de señal como recibido en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de ruido recibido en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de ruido recibido en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de señal enviado en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de señal enviado en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de ruido enviado en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de ruido enviado en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

