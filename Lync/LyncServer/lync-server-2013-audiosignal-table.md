---
title: 'Lync Server 2013: Tabla AudioSignal'
TOCTitle: Tabla AudioSignal
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48274222
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tabla AudioSignal en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Cada registro representa las métricas de señales de audio para un extremo. Por lo general, cada llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario de la llamada.


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
<td><p>Se obtiene de <a href="lync-server-2013-medialine-table.md">Tabla MediaLine en Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>Int</p></td>
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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Representa el nivel de señal de audio del control de ganancia postanalógico. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser de al menos 30 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Consulte SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Representa el nivel de ruido de audio del control de ganancia postanalógico. La unidad de esta métrica es dBmo. Para que la calidad sea aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Consulte SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Métrica de mejora de la pérdida del retorno de eco. La unidad de esta métrica es dB. Los valores inferiores representan un eco menor. El servidor de conferencia A/V y los teléfonos IP no notifican esta métrica.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Número medio de problemas generados cada cinco minutos para la presentación del altavoz. Para que la calidad sea buena, debe ser inferior a uno cada cinco minutos. No se notifica en los servidores de conferencia A/V, los servidores de mediación ni los teléfonos IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Número medio de problemas generados cada cinco minutos para la captura del micrófono. Para que la calidad sea buena, debe ser inferior a uno cada cinco minutos. No se notifica en los servidores de conferencia A/V, los servidores de mediación ni los teléfonos IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Índice de desfase del reloj del dispositivo del micrófono, con respecto al reloj de la CPU.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Índice de desfase del reloj del dispositivo del altavoz, con respecto al reloj de la CPU.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Índice de desfase del reloj del dispositivo del altavoz, con respecto al reloj de la CPU.</p>
<p>Número medio de errores en marcas de tiempo de secuencia de captura del micrófono, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Número medio de errores en marcas de tiempo de secuencia de presentación del altavoz, en milisegundos, en los últimos 20 segundos de la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>La conmutación de voz es un modo de dúplex medio con capacidad de interrupción reducida. Causas de una entrada de conmutación de voz:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>La causa puede ser una combinación de esas causas individuales. ENTER_VS_FORCEORCONVERGENCE solo se puede habilitar en regkey para fines de pruebas.</p>
<p>El tipo de datos para esta columna se cambió en Microsoft Lync Server 2013.</p></td>
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
<p>La causa puede ser una combinación de causas individuales.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Porcentaje de tiempo para la detección del eco en la secuencia enviada. Un porcentaje alto de eco en las secuencias enviadas indica la presencia de filtraciones de eco.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Nivel de la señal recibida en el servidor de mediación desde la puerta de enlace. Solamente se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para que la calidad sea buena, el rango aceptable debe ser de [-30 a -18] dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Nivel de la señal recibida en el servidor de mediación desde la puerta de enlace. Solamente se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para que la calidad sea buena, el rango aceptable debe ser inferior a -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Control de ganancia automático (AGC) en el servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>RMS de entrada de los primeros 30 segundos de la llamada como máximo.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>El nivel de señal según se recibe en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>El nivel de señal según se recibe en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nivel de ruido según se recibe en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nivel de ruido según se recibe en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nivel de señal según se envía en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nivel de señal según se envía en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nivel de ruido según se envía en el canal 1.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nivel de ruido según se envía en el canal 2.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

