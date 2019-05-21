---
title: Tabla AudioStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Cada registro representa una secuencia de audio. Una línea de medios de audio normalmente contiene dos secuencias de audio.
ms.openlocfilehash: eae96b08f3a365288f48b7a68c75d3fd9114107d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295051"
---
# <a name="audiostream-table"></a>Tabla AudioStream
 
Cada registro representa una secuencia de audio. Una línea de medios de audio normalmente contiene dos secuencias de audio.
  
|Columna|Tipo de datos|Clave o índice|Detalles|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |IDENTIFICADOR exclusivo dentro de una línea de medios.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|**PacketLossRate** <br/> |decimal (4,5)  <br/> | <br/> |Tasa promedio de pérdida de paquetes durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal (4,5)  <br/> | <br/> |Pérdida máxima de paquetes observadas durante la llamada.  <br/> |
|**BurstDensity** <br/> |decimal (9, 4)  <br/> | <br/> |Densidad promedio de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|**BurstGapDensity** <br/> |decimal (9, 4)  <br/> | <br/> |Densidad media de pérdida de paquetes entre ráfagas de pérdida de paquetes.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Duración media de los huecos entre las ráfagas de pérdida de paquetes.  <br/> |
|**PacketUtilization** <br/> |ENT  <br/> | <br/> |Recuento de paquetes de la secuencia de audio.  <br/> |
|**Ancho de banda más** <br/> |ENT  <br/> | <br/> |Cálculo de ancho de banda para la secuencia de audio.  <br/> |
|**DegradationAvg** <br/> |decimal (3, 2)  <br/> | <br/> |Degradación de MOS de red para toda la llamada. El intervalo está comprendido entre 0,0 y 5,0. Esta métrica muestra el monto que se redujo en el MOS de red debido a la vibración y a la pérdida de paquetes. Para una calidad aceptable, debe ser menor que 0,5.  <br/> |
|**DegradationMax** <br/> |decimal (3, 2)  <br/> | <br/> |La degradación de OP máxima de red durante la llamada.  <br/> |
|**DegradationJitterAvg** <br/> |decimal (3, 2)  <br/> | <br/> |Degradación de MOS de red causada por vibración.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal (3, 2)  <br/> | <br/> |Degradación de MOS de red causada por pérdida de paquetes.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Extranjero  <br/> |El códec de audio usado para la llamada, al que se hace referencia desde la tabla PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Frecuencia de muestreo de la secuencia de audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP. Para obtener una calidad aceptable, debe ser inferior a 100 $.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tiempo máximo de ida y vuelta para la secuencia de audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal (3, 2)  <br/> | <br/> |MOS de red de banda ancha promedio para la llamada. Esta métrica depende de la pérdida del paquete, de la vibración y del códec usado. El rango es de [1,0 a 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal (3, 2)  <br/> | <br/> |MOS de red de banda ancha mínima para la llamada.  <br/> |
|**SendListenMOS** <br/> |decimal (3, 2)  <br/> | <br/> |La puntuación media de escucha de banda ancha prevista para el audio enviado, incluyendo el nivel de voz, el nivel de ruido y las características del dispositivo de captura.  <br/> |
|**SendListenMOSMin** <br/> |decimal (3, 2)  <br/> | <br/> |El SendListenMOS mínimo para la llamada.  <br/> |
|**RecvListenMOS** <br/> |decimal (3, 2)  <br/> | <br/> |La puntuación media de escucha de banda ancha prevista para el audio recibido de la red, incluido el nivel de voz, el nivel de ruido, el códec, las condiciones de la red y las características del dispositivo de captura.  <br/> |
|**RecvListenMOSMin** <br/> |decimal (3, 2)  <br/> | <br/> |El RecvListenMOS mínimo para la llamada.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Marca que indica si se usó el audio FEC para la llamada.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal (4,5)  <br/> ||Relación media entre las muestras ocultas generadas por la corrección de audio a muestras típicas.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal (4,5)  <br/> ||Relación media de muestras extendidas generadas por la recuperación de audio a muestras típicas.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal (4,5)  <br/> ||Relación media de muestras comprimidas generadas por la corrección de audio a muestras típicas.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Se reciben los datos de la secuencia del lado del destinatario.  <br/> |
|**Saliente** <br/> |bit  <br/> | <br/> |Se reciben los datos de la secuencia en el lado del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada.  <br/> 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Desviación estándar para las horas de llegada de la vibración.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Relación máxima de paquetes ocultos por el Healer.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Desviación estándar para la proporción de paquetes ocultos por el Healer.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Proporción de paquetes descartados por el healro comparado con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Relación entre los paquetes de corrección de errores de reenvío en comparación con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Número máximo de paquetes de audio que el Healer ha comprimido.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la hora en que la llamada se encontraba en un estado de congestión de pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada demorada de los paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje de la hora en que la llamada compite en los recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Cantidad mínima de estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Cantidad máxima de estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desviación estándar de la estimación del ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Cantidad promedio de estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de repeticiones de ráfagas unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Total de duración de ráfaga unidireccional. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de repeticiones de intervalos unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad de brechas en un camino total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración del intervalo unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada descodificada como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada representada como estéreo por el cancelador de eco acústico.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada codificada como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada capturada como estéreo por el cancelador de eco acústico.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
