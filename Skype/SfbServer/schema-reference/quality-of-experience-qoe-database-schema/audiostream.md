---
title: Tabla AudioStream
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Cada registro representa una secuencia de audio. Una línea de medios de audio normalmente contiene dos secuencias de audio.
ms.openlocfilehash: 28111f9c97efdc729d13fda824f4236caad97eee1f08ff31eea0b751dda1cb88
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309199"
---
# <a name="audiostream-table"></a>Tabla AudioStream
 
Cada registro representa una secuencia de audio. Una línea de medios de audio normalmente contiene dos secuencias de audio.
  
|Columna|Tipo de datos|Clave/índice|Detalles|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |Entero  <br/> |Principal  <br/> |Identificador único de una línea de medios.  <br/> |
|**JitterInterArrival** <br/> |Entero  <br/> | <br/> |Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |Entero  <br/> | <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Promedio de frecuencia de pérdida de paquetes durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Pérdida máxima de paquetes observada durante la llamada.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidad media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|**BurstDuration** <br/> |Entero  <br/> | <br/> |Duración media de la pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidad media de pérdida de paquetes durante los intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|**BurstGapDuration** <br/> |Entero  <br/> | <br/> |Duración media de los intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Recuento de paquetes para la secuencia de audio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Previsiones de ancho de banda de la secuencia de audio.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red para toda la llamada. El intervalo es de 0,0 a 5,0. Esta métrica muestra la cantidad que se redujo el MOS de red debido a la vibración y la pérdida de paquetes. Para una calidad aceptable debe ser inferior a 0,5.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Degradación máxima de MOS de red durante la llamada.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red causada por el jitter.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red causada por la pérdida de paquetes.  <br/> |
|**AudioPayloadDescription** <br/> |Entero  <br/> |Externo  <br/> |Códec de audio usado para la llamada, al que se hace referencia desde PayloadDescription Table.  <br/> |
|**AudioSampleRate** <br/> |Entero  <br/> | <br/> |Velocidad de muestreo de la secuencia de audio.  <br/> |
|**RoundTrip** <br/> |Entero  <br/> | <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP. Para una calidad aceptable, debe ser inferior a 100 ms.  <br/> |
|**RoundTripMax** <br/> |Entero  <br/> | <br/> |Tiempo de ida y vuelta máximo de la secuencia de audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Promedio de MOS de red de banda ancha para la llamada. Esta métrica depende de la pérdida de paquetes, el vibración y el códec usados. El intervalo es [1,0 a 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS de red de banda ancha mínima para la llamada.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |La puntuación media de MOS de escucha de banda ancha pronosticada para el audio enviado, incluidos el nivel de voz, el nivel de ruido y las características del dispositivo de captura.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |El valor mínimo de SendListenMOS para la llamada.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |La puntuación media de MOS de escucha de banda ancha pronosticada para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y las características del dispositivo de captura.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |Mínimo RecvListenMOS para la llamada.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Marca que indica si se usó AUDIO FEC para la llamada.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Relación media de muestras ocultas generadas por la recuperación de audio con las muestras típicas.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Relación media de muestras estiradas generadas por la recuperación de audio a muestras típicas.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Relación media de muestras comprimidas generadas por la recuperación de audio a muestras típicas.  <br/> |
|**Entrante** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del receptor.  <br/> |
|**Salida** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de la secuencia es del autor de la llamada al destinatario de la llamada.  <br/> 0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Desviación estándar para las horas de llegada de vibración.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Relación máxima de paquetes ocultos por el sanador.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Desviación estándar para la relación de paquetes ocultados por el sanador.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Relación de paquetes descartados por el sanador en comparación con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Relación de paquetes de corrección de errores de reenvío usados en comparación con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Número máximo de paquetes de audio comprimidos por el sanador.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo en que la llamada estaba en estado de congestión de pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante la cual la congestión se produjo por la llegada retrasada de paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo en que la llamada competía por los recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |Entero  <br/> ||Cantidad mínima de estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |Entero  <br/> ||Cantidad máxima de estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |Entero  <br/> ||Desviación estándar de la estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |Entero  <br/> ||Cantidad media de estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |Entero  <br/> ||Cantidad total de ráfagas unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad total de ráfagas unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración total de ráfagas unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |Entero  <br/> ||Cantidad total de intervalos unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad total de intervalos unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración total de intervalos unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada descodificada como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada que el cancelador de eco acústico representa como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada codificada como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada capturada como estéreo por el cancelador de eco acústico.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
