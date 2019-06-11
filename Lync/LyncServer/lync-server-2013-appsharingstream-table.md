---
title: 'Lync Server 2013: tabla AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Tabla AppSharingStream en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-21_

La tabla AppSharingStream contiene métricas de experiencia de calidad para las secuencias de red que se usan para compartir aplicaciones. Esta tabla se introdujo en Microsoft Lync Server 2013.


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
<td><p>Fechas</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Fecha y hora en que comenzó la sesión.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Identificador secuencial que se usa para diferenciar las sesiones que comenzaron en la misma fecha y al mismo tiempo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal, extranjero</p></td>
<td><p>Representa el tipo de línea de vídeo que se usa en la llamada. Los valores permitidos son:</p>
<ul>
<li><p>0: audio</p></li>
<li><p>1: vídeo</p></li>
<li><p>2-video panorámico</p></li>
<li><p>3: uso compartido de aplicaciones y escritorio</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Identificador único de la secuencia de uso compartido de aplicaciones.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Vibración máxima detectada entre las llegadas al paquete RTP. (La vibración es una medida de &quot;la irregularidad&quot; de una llamada). Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Cantidad máxima de (en milisegundos) necesaria para que un paquete de protocolo de transporte en tiempo real viaje a otro extremo y después de nuevo. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.</p>
<p>Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tasa máxima de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes RTP, un protocolo usado para transmitir audio y vídeo a través de Internet, no pudo alcanzar su destino). Las tarifas de pérdida elevada suelen ser causadas por la congestión; falta de ancho de banda; disgestión o interferencias inalámbricas; o un servidor multimedia sobrecargado. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de paquetes enviados.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ancho de banda más</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ancho de banda de unidireccional Estimado disponible al final de la sesión. Se notifica en bits por segundo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Descripción de la carga de uso compartido de aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de repeticiones de ráfagas unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Total de duración de ráfaga unidireccional. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de repeticiones de intervalos unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de brechas en un camino total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del intervalo unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256)</p></td>
<td></td>
<td><p>Función de aplicación (persona que comparte o visor) y tipo de contenido.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tiempo total de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP). Un total más alto iguala a un retraso más largo en la experiencia de visualización.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tiempo promedio de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP). Un total más alto iguala a un retraso más largo en la experiencia de visualización.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tiempo máximo de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP). Un total más alto iguala a un retraso más largo en la experiencia de visualización.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de ráfagas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración de ráfagas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de huecos en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de brechas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). La densidad de huecos bajos corresponde a una mejor experiencia de visualización.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del hueco en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Las duraciones cortas equivalen a una mejor experiencia de visualización.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tasa total de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Velocidad promedio de los mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Frecuencia máxima de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>en t</p></td>
<td></td>
<td><p>Repeticiones de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de huecos en la tasa de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de huecos en la tasa de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del hueco en la tasa de mosaicos capturados (en mosaicos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentaje total del contenido que no se ha podido alcanzar con el visor, pero que se ha descartado y ha sido reemplazado por contenido nuevo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentaje medio del contenido que no se ha encontrado en el visor pero que se ha descartado y se ha reemplazado por contenido nuevo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentaje máximo del contenido que no se ha podido alcanzar con el visor, pero que se descartó y se sobrescribió por contenido nuevo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de ráfagas para el contenido que no se ha podido alcanzar con el visor, pero que se han descartado y reemplazado por contenido nuevo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga para el contenido que no se ha podido alcanzar con el visor, pero se ha descartado y ha sido reemplazado por contenido nuevo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración de ráfaga para el contenido que no se ha podido alcanzar con el visor, pero se ha descartado y ha sido reemplazado por contenido nuevo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Las repeticiones de huecos para el contenido que no se ha podido alcanzar con el visor pero se han descartado y reemplazado por contenido nuevo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de brechas para el contenido que no se ha podido alcanzar con el visor, pero que se descartó y sobrescribe por contenido nuevo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>El intervalo de tiempo para el contenido que no se ha podido alcanzar con el visor, se ha descartado y ha sido reemplazado por contenido nuevo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número total de fotogramas descartados de la fuente de gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número promedio de fotogramas descartados del origen de gráficos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número máximo de fotogramas descartados del origen de gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de ráfagas en los fotogramas descartados de la fuente de gráficos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga en las tramas descartadas de la fuente de gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración de ráfaga en las tramas descartadas del origen de gráficos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de huecos en los fotogramas descartados del origen de los gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de huecos en los fotogramas descartados del origen de gráficos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del hueco en los fotogramas descartados del origen de los gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Total de la velocidad de fotogramas entrantes recibida por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Promedio de velocidad de fotogramas entrante recibida por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad máxima de mosaico entrante recibida por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de ráfaga en la tasa de mosaico entrante recibida por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga en la tasa de icono entrante recibida por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración de ráfaga en la tasa de mosaico entrante recibida por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Las repeticiones de huecos de la velocidad de los mosaicos entrantes recibidas por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de hueco en la tasa de mosaico entrante recibida por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del intervalo en la tasa de mosaico entrante recibida por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Total de la velocidad de fotogramas entrantes recibida por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Promedio de velocidad de fotogramas entrante recibida por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cantidad máxima de fotogramas entrantes recibida por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de ráfagas en la velocidad de fotogramas entrantes recibidas por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga en la velocidad de fotogramas entrantes recibida por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>La duración de la ráfaga en la velocidad de fotogramas entrante recibida por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Las repeticiones de huecos de la velocidad de fotogramas entrantes recibidas por el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de huecos en la velocidad de fotogramas entrante recibida por el visor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del hueco en la velocidad de fotogramas entrante que recibió el visor.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Intervalo total de los mosaicos salientes del remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Promedio de la velocidad de los iconos salientes del remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Velocidad máxima de los iconos salientes del remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de ráfaga en la tasa del mosaico saliente para el remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfaga en la tasa del mosaico saliente para el remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración de ráfaga en la tasa del mosaico saliente para el remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de huecos en la tasa de mosaico saliente para el remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de hueco en la tasa de mosaico saliente para el remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del hueco en la tasa del mosaico saliente para el remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Total de la velocidad de los fotogramas salientes del remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>promedio de velocidad de fotograma saliente para el remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Velocidad máxima de los fotogramas salientes del remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de ráfagas en la velocidad de fotogramas salientes del remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de ráfagas en la velocidad de fotogramas salientes del remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración de ráfaga en la velocidad de fotogramas salientes del remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Repeticiones de huecos en la velocidad de fotogramas salientes del remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidad de huecos en la velocidad de fotogramas salientes del remitente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duración del hueco en la velocidad de fotogramas salientes del remitente.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Promedio de altura de la resolución de video, en píxeles.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Promedio de ancho de resolución de video, en píxeles.</p></td>
</tr>
<tr class="even">
<td><p><strong>Entrada</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Promedio de velocidad de fotogramas (en fotogramas por segundo) para transfronterizas entrantes.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saliente</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Promedio de velocidad de fotogramas (en fotogramas por segundo) para transfronterizas salientes.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>1 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</p>
<p>0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

