---
title: 'Lync Server 2013: Tabla AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Tabla AudioStream en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Cada registro representa una secuencia de audio. Una línea de medios de audio normalmente contiene dos secuencias de audio.


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
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>IDENTIFICADOR exclusivo dentro de una línea de medios.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Vibración máxima de la red durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Tasa promedio de pérdida de paquetes durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td><p> </p></td>
<td><p>Pérdida máxima de paquetes observadas durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Densidad promedio de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Densidad media de pérdida de paquetes entre ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Duración media de los huecos entre las ráfagas de pérdida de paquetes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>ENT</p></td>
<td><p> </p></td>
<td><p>Recuento de paquetes de la secuencia de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ancho de banda más</strong></p></td>
<td><p>ENT</p></td>
<td><p> </p></td>
<td><p>Cálculo de ancho de banda para la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Degradación de MOS de red para toda la llamada. El intervalo está comprendido entre 0,0 y 5,0. Esta métrica muestra el monto que se redujo en el MOS de red debido a la vibración y a la pérdida de paquetes. Para una calidad aceptable, debe ser menor que 0,5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>La degradación de OP máxima de red durante la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Degradación de MOS de red causada por vibración.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>Degradación de MOS de red causada por pérdida de paquetes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Extranjero</p></td>
<td><p>El códec de audio usado para la llamada, al que se hace referencia desde la tabla PayloadDescription.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Frecuencia de muestreo de la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tiempo de ida y vuelta de las estadísticas de RTCP. Para obtener una calidad aceptable, debe ser inferior a 100 $.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tiempo máximo de ida y vuelta para la secuencia de audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>MOS de red de banda ancha promedio para la llamada. Esta métrica depende de la pérdida del paquete, de la vibración y del códec usado. El rango es de [1,0 a 5,0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>MOS de red de banda ancha mínima para la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>La puntuación media de escucha de banda ancha prevista para el audio enviado, incluyendo el nivel de voz, el nivel de ruido y las características del dispositivo de captura.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>El SendListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>La puntuación media de escucha de banda ancha prevista para el audio recibido de la red, incluido el nivel de voz, el nivel de ruido, el códec, las condiciones de la red y las características del dispositivo de captura.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>decimal (3, 2)</p></td>
<td><p> </p></td>
<td><p>El RecvListenMOS mínimo para la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Marca que indica si se usó el audio FEC para la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td></td>
<td><p>Relación media entre las muestras ocultas generadas por la corrección de audio a muestras típicas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td></td>
<td><p>Relación media de muestras extendidas generadas por la recuperación de audio a muestras típicas.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>decimal (4,5)</p></td>
<td></td>
<td><p>Relación media de muestras comprimidas generadas por la corrección de audio a muestras típicas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Entrada</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Se reciben los datos de la secuencia del lado del destinatario.</p></td>
</tr>
<tr class="even">
<td><p><strong>Saliente</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Se reciben los datos de la secuencia en el lado del remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada.</p>
<p>0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Desviación estándar para las horas de llegada de la vibración.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Relación máxima de paquetes ocultos por el Healer.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Desviación estándar para la proporción de paquetes ocultos por el Healer.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Proporción de paquetes descartados por el healro comparado con el número total de paquetes recibidos.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Relación entre los paquetes de corrección de errores de reenvío en comparación con el número total de paquetes recibidos.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número máximo de paquetes de audio que el Healer ha comprimido.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica el porcentaje de la hora en que la llamada se encontraba en un estado de congestión de pérdida.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada demorada de los paquetes de red.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica el porcentaje de la hora en que la llamada compite en los recursos de red.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Cantidad mínima de estimación del ancho de banda medido durante la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Cantidad máxima de estimación del ancho de banda medido durante la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Desviación estándar de la estimación del ancho de banda medida durante la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Cantidad promedio de estimación del ancho de banda medido durante la llamada.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de repeticiones de ráfagas unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Total de duración de ráfaga unidireccional. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de repeticiones de intervalos unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de brechas en un camino total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del intervalo unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentaje de la llamada descodificada como estéreo.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentaje de la llamada representada como estéreo por el cancelador de eco acústico.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentaje de la llamada codificada como estéreo.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentaje de la llamada capturada como estéreo por el cancelador de eco acústico.</p>
<p>Esta columna se introdujo en Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

