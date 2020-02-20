---
title: 'Lync Server 2013: tabla AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d09842cb8b905798855cef7e015e4d9b32e72dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Tabla AudioSignal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-12_

Cada registro representa métricas de señal de audio para un punto de conexión. Normalmente, cada llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Representa el nivel de señal de audio de control de ganancia posterior analógico. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consulte SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Representa el nivel de ruido de audio del control de ganancia posterior analógico. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consulte SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Métrica de mejora de pérdida de devolución de eco. La unidad para esta métrica es dB. Los valores inferiores representan menos eco. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Media de problemas por cinco minutos para la representación del altavoz. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Media de problemas por cinco minutos para la captura del micrófono. Para una buena calidad, debe ser inferior a uno por cinco minutos. No notificado por los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Tasa de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Tasa de desplazamiento del reloj de dispositivo de altavoz, relativa al reloj de la CPU.</p>
<p>Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Error medio de marca de tiempo de la secuencia de representación del altavoz, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Causas de la entrada de conmutación de voz:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>La causa puede ser una combinación de causas individuales. RegKey solo puede habilitar ENTER_VS_FORCEORCONVERGENCE mediante RegKey con fines de prueba.</p>
<p>El tipo de datos para esta columna se modificó en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Causas de un evento ECHO:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>La causa puede ser una combinación de causas individuales.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de tiempo durante el que se detectó el eco en la secuencia de captura del micrófono. Normalmente, los valores son bajos para auriculares o auriculares, y más arriba para los teléfonos de altavoces o los altavoces autónomos. Para los dispositivos que admiten la cancelación del eco acústico en la tarjeta, los valores altos indican la pérdida de eco. Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal (5, 2)</p></td>
<td></td>
<td><p>Porcentaje de tiempo en que se detecta eco en la secuencia enviada. Porcentaje de eco alto en secuencias de envío una indicación de pérdida de eco.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el intervalo aceptable debe ser [-30 a-18] dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nivel de señal recibido en el servidor de mediación de la puerta de enlace. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el intervalo aceptable debe ser inferior a-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Control de ganancia automático (AGC) en el servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>El cuadrado raíz medio (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de señal tal y como se recibe en el canal 1.</p>
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
<td><p>Nivel de ruido según se recibe en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de ruido que se recibe en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de señal como enviado en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nivel de señal como enviado en el canal 2.</p>
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

