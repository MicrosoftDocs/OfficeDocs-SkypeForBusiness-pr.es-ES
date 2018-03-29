---
title: Tabla AudioStream
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Cada registro representa una secuencia de audio. Normalmente, una línea media audio contiene dos secuencias de audio.
ms.openlocfilehash: 63cd2f63eed5d423750a50a23ae347a97725d65f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="audiostream-table"></a>Tabla AudioStream
 
Cada registro representa una secuencia de audio. Normalmente, una línea media audio contiene dos secuencias de audio.
  
|Columna ***|Tipo de datos ***|Clave o índice ***|Detalles ***|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Id. único dentro de la línea media.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Vibración de red promedio de las estadísticas de protocolo de Control de tiempo Real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Velocidad de pérdida de paquetes promedio durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Pérdida de paquete máximo observada durante la llamada.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidad media de pérdida de paquetes durante las ráfagas de las pérdidas durante la llamada.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Duración media de pérdida de paquetes durante las ráfagas de las pérdidas durante la llamada.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Duración media de los espacios entre ráfagas de pérdida de paquetes.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Recuento de paquetes para la secuencia de audio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Estimaciones de ancho de banda para la secuencia de audio.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de MOS de red para la llamada entera. Rango es 0.0 a 5.0. Esta métrica muestra el importe que se ha reducido el MOS de red debido a la inestabilidad y pérdida de paquetes. Para una calidad aceptable debe menor que 0,5.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de red MOS máximo durante la llamada.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de la red MOS causada por vibración.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradación de la red MOS causada por la pérdida de paquetes.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Externa  <br/> |El códec de audio utilizado para la llamada, se hace referenciada en la tabla PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Tasa de muestreo de la secuencia de audio.  <br/> |
|**Ida y vuelta** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta desde estadísticas RTCP. Debe ser inferior a 100 ms de calidad aceptable.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta máximo para la secuencia de audio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Promedio de banda ancha MOS de red para la llamada. Esta métrica depende de la pérdida de paquetes, la inestabilidad y el códec utilizado. Intervalo es [1.0 a 5.0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |El mínimo wideband MOS de red para la llamada.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS de escucha de wideband predicción promedio puntuación para audio enviado, incluyendo el nivel de voz, ruido y las características del dispositivo de captura.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |El mínimo SendListenMOS para la llamada.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |La puntuación de escucha MOS promedio wideband prevista para audio recibido de la red incluyendo el nivel de voz, nivel de ruido, códec, las condiciones de red y las características del dispositivo de captura.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |El mínimo RecvListenMOS para la llamada.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Marcador que indica si se utilizó FEC de audio para la llamada.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Promedio de muestras ocultas generados por audio sanación a ejemplos típicos.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Promedio de muestras estiradas generados por audio sanación a ejemplos típicos.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Promedio de muestras comprimidas generado por audio sanación a ejemplos típicos.  <br/> |
|**De entrada** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del receptor.  <br/> |
|**Salida** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de flujo es desde el llamador al destinatario de la llamada.  <br/> 0 significa que la dirección de flujo es del destinatario de la llamada al llamador.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Desviación estándar para las horas de llegada de vibración.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Relación máxima de paquetes ocultado por el sanador.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Desviación estándar de la proporción de paquetes ocultado por el sanador.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Relación de paquetes descartados por el sanador en comparación con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Relación entre paquetes de corrección de errores de reenvío usado en comparación con el número total de paquetes recibidos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Número máximo de paquetes que se han comprimido por el sanador.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje del tiempo cuando la llamada se encontraba en un estado de congestión de pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada retrasada de paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje del tiempo cuando la llamada competía para recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Importe mínimo de la estimación del ancho de banda se mide durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Cantidad máxima de la estimación del ancho de banda se mide durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desviación estándar de la estimación del ancho de banda se mide durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Mide la cantidad promedio de la estimación del ancho de banda durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Promedio de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Apariciones de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración total de ráfagas unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Apariciones de la total separación unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad total brecha unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración total brecha unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada descifrada como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada representada como estéreo por el cancelador de eco acústico.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Velocidad de pérdida de paquetes, después de aplicar la corrección de errores.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada que se codifican como estéreo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Porcentaje de la llamada capturada como estéreo por el cancelador de eco acústico.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

