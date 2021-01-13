---
title: Tabla VideoStream
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Cada registro representa una secuencia de vídeo. Normalmente, una línea de medios de vídeo contiene dos secuencias de vídeo.
ms.openlocfilehash: e506f022dbfa4ef0a1a8578dc6caf7c0f3984fa6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821330"
---
# <a name="videostream-table"></a>Tabla VideoStream
 
Cada registro representa una secuencia de vídeo. Normalmente, una línea de medios de vídeo contiene dos secuencias de vídeo.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |entero  <br/> |Principal  <br/> |R a la que se hace referencia desde [la tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |entero  <br/> |Principal  <br/> |Identificador único de una línea de medios.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Externa, Principal  <br/> |Descripción de la carga útil. Consulta la [tabla PayloadDescription](payloaddescription.md) para obtener más información. <br/> |
|**JitterInterArrival** <br/> |entero  <br/> | <br/> |Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |entero  <br/> | <br/> |Vibración de red máxima durante la sesión de vídeo.  <br/> |
|**RoundTrip** <br/> |entero  <br/> | <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP.  <br/> |
|**RoundTripMax** <br/> |entero  <br/> | <br/> |Tiempo máximo de ida y vuelta para la secuencia de vídeo.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Promedio de frecuencia de pérdida de paquetes durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Pérdida máxima de paquetes observada durante la llamada.  <br/> |
|**PacketUtilization** <br/> |entero  <br/> | <br/> |Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).  <br/> |
|**BandwidthEst** <br/> |entero  <br/> | <br/> |Estimaciones de ancho de banda para la secuencia de vídeo.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Resolución del vídeo en píxeles de ancho multiplicados por píxeles de alto. Se proporciona como cadena.  <br/> |
|**VideoBitRateAvg** <br/> |entero  <br/> | <br/> |Tasa de bits media de la secuencia de vídeo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Velocidad de fotogramas de vídeo recibida.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |Velocidad de fotogramas de vídeo enviada.  <br/> |
|**VideoBitRateMax** <br/> |entero  <br/> | <br/> |Velocidad de bits de vídeo máxima durante la sesión de vídeo.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |Porcentaje del total de fotogramas de vídeo que se pierden.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |No disponible.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||Porcentaje del total de fotogramas de vídeo que se pierden.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Porcentaje de la llamada que estaba en la resolución de formato de intercambio común (CIF).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Porcentaje de la llamada que estaba en resolución VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Porcentaje de la llamada que estaba en resolución HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada sin colocar fotogramas.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con la colocación de fotograma B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con la colocación de fotogramas de BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con la colocación de fotogramas BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con la colocación de fotogramas BPSPI.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del receptor.  <br/> |
|**Saliente** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia en el lado del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.  <br/> 0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo en que la llamada estaba en estado de congestión de pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante la cual la congestión se produjo por la llegada retrasada de paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo en que la llamada compitía por los recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |entero  <br/> ||Cantidad mínima de estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |entero  <br/> ||Cantidad máxima de estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |entero  <br/> ||Desviación estándar de la estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |entero  <br/> ||Cantidad media de estimación de ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Porcentaje de la llamada en la que el punto de conexión determinó que la conexión de red no podía admitir vídeo de vista múltiple.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |entero  <br/> ||Cantidad total de ráfagas unidireccionales. Una transmisión "con ráfagas" es una transmisión en la que los datos fluyen con ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |entero  <br/> ||Densidad total de ráfagas unidireccionales. Una transmisión "con ráfagas" es una transmisión en la que los datos fluyen con ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración total de ráfagas unidireccionales. Una transmisión "con ráfagas" es una transmisión en la que los datos fluyen con ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |entero  <br/> ||Cantidad total de intervalos unidireccionales. Una transmisión "con ráfagas" es una transmisión en la que los datos fluyen con ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad total de intervalos unidireccionales. Una transmisión "con ráfagas" es una transmisión en la que los datos fluyen con ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración total de intervalos unidireccionales. Una transmisión "con ráfagas" es una transmisión en la que los datos fluyen con ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Tasa a la que se perdieron los paquetes de vídeo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |entero  <br/> ||Cantidad máxima del ancho de banda asignada para vídeo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Externo  <br/> |Tipo de códecs de vídeo usados por el remitente. Consulta la [tabla CodecDescription](codecdescription.md) para obtener más información. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |entero  <br/> ||Ancho de resolución usado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |entero  <br/> ||Alto de resolución usado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Transmisión media de velocidad de fotogramas de vídeo usada por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |entero  <br/> ||Velocidad de bits máxima para el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |entero  <br/> ||Velocidad de bits media para el remitente.  <br/> |
|**SendVideoStreamsMax** <br/> |entero  <br/> ||Número máximo de secuencias de vídeo usadas por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Externo  <br/> |Códigos de vídeo usados por el receptor. Consulta la [tabla CodecDescription](codecdescription.md) para obtener más información. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |entero  <br/> ||Ancho de resolución usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |entero  <br/> ||Alto de resolución usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Velocidad media de fotogramas de vídeo usada por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |entero  <br/> ||Velocidad de bits máxima para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |entero  <br/> ||Velocidad de bits media para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |entero  <br/> ||Máximo de secuencias de vídeo para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |entero  <br/> ||Secuencias de vídeo mínimas para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |entero  <br/> ||Modo de vídeo (por ejemplo, galería o secuencia única) para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Porcentaje de tiempo durante el que la marca de capacidad dinámica estaba activa.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Resolución mínima medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de velocidad de bits baja (70 kilobits por segundo).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de velocidad de fotogramas baja (7,5 fotogramas por segundo, entrante).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada que se produjo en la resolución más baja.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Duración de la llamada en segundos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica si los datos se han agregado desde varias llamadas.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

