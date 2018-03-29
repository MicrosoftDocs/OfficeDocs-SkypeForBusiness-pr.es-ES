---
title: Tabla VideoStream
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Cada registro representa una secuencia de vídeo. Una línea de vídeo media normalmente contiene dos secuencias de vídeo.
ms.openlocfilehash: 27a9c8cdd8b1975b7854147b5855a8494155ce2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="videostream-table"></a>Tabla VideoStream
 
Cada registro representa una secuencia de vídeo. Una línea de vídeo media normalmente contiene dos secuencias de vídeo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R hace referencia en la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Id. único dentro de la línea media.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Principal, externa  <br/> |Descripción de la carga. Consulte la [tabla de PayloadDescription](payloaddescription.md) para obtener más información. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Vibración de red promedio de las estadísticas de protocolo de Control de tiempo Real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Vibración máxima de la red durante la sesión de video.  <br/> |
|**Ida y vuelta** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta desde estadísticas RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta máximo para la secuencia de vídeo.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Velocidad de pérdida de paquetes promedio durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Pérdida de paquete máximo observada durante la llamada.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo Real, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Estimaciones de ancho de banda para la secuencia de vídeo.  <br/> |
|**VideoResolution** <br/> |Char (9)  <br/> | <br/> |Resolución del vídeo en el ancho de píxeles multiplicado por alto de píxeles. El informe como una cadena.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Velocidad promedio de bits de la secuencia de vídeo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |La velocidad de fotograma de vídeo que se reciben.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Velocidad de fotograma de vídeo que se envía.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |La velocidad de bits de vídeo máxima durante la sesión de video.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |El porcentaje total de cuadros de vídeo que se pierden.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |No está disponible.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||El porcentaje total de cuadros de vídeo que se pierden.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que estaba en la resolución del formato de intercambio común (CIF).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que era con resolución VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que estaba en la resolución de HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada con ninguna gota de marco.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con la colocación de marco de B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con la colocación de marco de BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada con la colocación de marco BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada con la colocación de marco BPSPI.  <br/> |
|**De entrada** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del receptor.  <br/> |
|**Salida** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de flujo es desde el llamador al destinatario de la llamada.  <br/> 0 significa que la dirección de flujo es del destinatario de la llamada al llamador.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje del tiempo cuando la llamada se encontraba en un estado de congestión de pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada retrasada de paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje del tiempo cuando la llamada competía para recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Importe mínimo de la estimación del ancho de banda se mide durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Cantidad máxima de la estimación del ancho de banda se mide durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desviación estándar de la estimación del ancho de banda se mide durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Mide la cantidad promedio de la estimación del ancho de banda durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Porcentaje de la llamada donde el extremo determina que la conexión de red no admite vídeo multiview.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Promedio de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Apariciones de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densidad de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración total de ráfagas unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Apariciones de la total separación unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad total brecha unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración total brecha unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Velocidad a la que se han perdido paquetes de video.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Cantidad promedio de ancho de banda asignado para el vídeo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Externa  <br/> |Tipo de códecs de vídeo utilizados por el remitente. Consulte la [tabla de CodecDescription](codecdescription.md) para obtener más información. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Ancho de resolución utilizado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Alto de resolución utilizado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Promedio de transmisión de velocidad de fotograma de vídeo utilizada por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Velocidad de bits máxima para el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Velocidad de bits promedio para el remitente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Número máximo de secuencias de vídeo utilizado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Externa  <br/> |Códigos de vídeo usados por el receptor. Consulte la [tabla de CodecDescription](codecdescription.md) para obtener más información. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Ancho de resolución usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Alto de resolución usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Velocidad de fotogramas de vídeo Media usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Velocidad de bits máxima para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Velocidad de bits promedio para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Secuencias de vídeo máximo para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Secuencias de vídeo mínimas para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modo de vídeo (por ejemplo, Galería o stream único) para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Velocidad de pérdida de paquetes, después de aplicar la corrección de errores.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Porcentaje de tiempo que el indicador de capacidad dinámica estaba activo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |Char (9)  <br/> ||Resolución mínima medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de velocidad de bits baja (70 kilobits por segundo).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de velocidad de fotogramas baja (7,5 fotogramas por segundo, de entrada).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada que se produjo en la resolución más baja.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Longitud de la llamada en segundos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica si los datos agregados de varias llamadas.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

