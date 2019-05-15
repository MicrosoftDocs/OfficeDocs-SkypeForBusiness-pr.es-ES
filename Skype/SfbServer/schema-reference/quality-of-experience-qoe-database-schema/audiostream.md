---
title: Tabla AudioStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Cada registro representa una secuencia de audio. Normalmente, una línea de medios de audio contiene dos secuencias de audio.
ms.openlocfilehash: b2360cc4e15a4c54508951d492e664493e983f0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920162"
---
# <a name="audiostream-table"></a>Tabla AudioStream
 
Cada registro representa una secuencia de audio. Normalmente, una línea de medios de audio contiene dos secuencias de audio.
  
|Columna|Tipo de datos|Clave o índice|Detalles|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Identificador único dentro de una línea de medios.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Vibración de red promedio de las estadísticas del protocolo de Control de tiempo Real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Frecuencia de pérdida de paquetes promedio durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Máximo la pérdida de paquetes observada durante la llamada.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidad media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidad media de pérdida de paquetes durante intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Duración media de intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Número de paquetes de la secuencia de audio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Previsiones de ancho de banda de la secuencia de audio.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red para la llamada completa. Rango es 0,0 a 5.0. Esta métrica muestra la cantidad que se ha reducido la MOS de red debido a la pérdida de paquetes y vibración. Para que una calidad aceptable debe menor que 0,5.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red máxima durante la llamada.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red provocada por la vibración.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red provocada por la pérdida.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Externa  <br/> |El códec de audio utilizado para la llamada, de PayloadDescription Table.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Velocidad de muestreo de la secuencia de audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta desde las estadísticas de RTCP. Debe ser inferior a 100 ms para calidad aceptable.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta máximo para la secuencia de audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Promedio de banda ancha MOS de red para la llamada. Esta métrica depende de la pérdida de paquetes, la vibración y el códec utilizado. Rango es [1.0 a 5.0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |El mínimo MOS banda ancha red de la llamada.  <br/> |
|**Valor de SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS de escucha de banda ancha prevista promedio puntuación audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |El valor de SendListenMOS mínimo para la llamada.  <br/> |
|**Valor de RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |La puntuación de MOS de escucha de banda ancha prevista promedio para el audio recibido desde la red, incluido el nivel de voz, el nivel de ruido, códec, las condiciones de red y las características del dispositivo de captura.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |El valor de RecvListenMOS mínimo para la llamada.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Marca que indica si se usó audio FEC para la llamada.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Relación media de muestras ocultas generadas por audio recuperación muestras típicas.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Relación media de muestras extendidas generadas por audio recuperación muestras típicas.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Relación media de muestras comprimidas generadas por audio recuperación muestras típicas.  <br/> |
|**De entrada** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia del receptor.  <br/> |
|**Saliente** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de secuencia desde el autor de la llamada hasta el destinatario de la llamada.  <br/> 0 indica que la dirección de secuencia desde el destinatario de la llamada al autor de la llamada.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Desviación estándar de las horas de llegada de vibración.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Relación máxima de paquetes ocultado por la muestra.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Desviación estándar de la relación de paquetes ocultado por la muestra.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Relación de paquetes descartados por la muestra comparados con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Relación de paquetes de corrección de errores de reenvío usados en comparación con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Número máximo de los paquetes de audio que comprimidos por la muestra.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo que la llamada estuvo en un estado de congestión pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante el cual la congestión estuvo causada por la llegada retrasada de paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo cuando la llamada estuvo compitiendo por recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Cantidad mínima de ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Cantidad máxima de ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desviación estándar de la estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||La cantidad promedio de ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada decodificada como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada representada como estéreo por el eliminador de eco acústico.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Tasa de pérdida de paquetes después de que se ha aplicado la corrección de errores de reenvío.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada codificada como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada capturada como estéreo por el eliminador de eco acústico.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
