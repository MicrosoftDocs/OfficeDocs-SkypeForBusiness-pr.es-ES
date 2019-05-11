---
title: Tabla VideoStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Cada registro representa una secuencia de vídeo. Normalmente, una línea de medios de vídeo contiene dos secuencias de vídeo.
ms.openlocfilehash: 59d0d0979513dc016912d7f4482f740c4ceeccd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925260"
---
# <a name="videostream-table"></a>Tabla VideoStream
 
Cada registro representa una secuencia de vídeo. Normalmente, una línea de medios de vídeo contiene dos secuencias de vídeo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R hace referencia en la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Identificador único dentro de una línea de medios.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Principal, externa  <br/> |Descripción de carga. Consulte la [tabla PayloadDescription](payloaddescription.md) para obtener más información. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Vibración de red promedio de las estadísticas del protocolo de Control de tiempo Real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Vibración máxima de la red durante la sesión de vídeo.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta desde las estadísticas de RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta máximo para la secuencia de vídeo.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Frecuencia de pérdida de paquetes promedio durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Máximo la pérdida de paquetes observada durante la llamada.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo Real, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Previsiones de ancho de banda de la secuencia de vídeo.  <br/> |
|**VideoResolution** <br/> |Char (9)  <br/> | <br/> |Resolución del vídeo en multiplicado por alto de píxeles de ancho de píxeles. El informe como una cadena.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Velocidad de bits Media de la secuencia de vídeo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |La velocidad de fotogramas de vídeo que se reciben.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |La velocidad de fotogramas de vídeo que se envía.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |La tasa de bits de vídeo máxima durante la sesión de vídeo.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |El porcentaje del total de fotogramas de vídeo que se pierden.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |No está disponible.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||El porcentaje del total de fotogramas de vídeo que se pierden.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que estaba en la resolución de formato de intercambio común (CIF).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que se realizó con resolución VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que se realizó con resolución HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con ninguna pérdida de fotogramas.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con pérdida de fotogramas B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con pérdida de fotogramas BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con fotogramas bpsp.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Porcentaje de duración de la llamada con fotogramas bpspi.  <br/> |
|**De entrada** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia del receptor.  <br/> |
|**Saliente** <br/> |bit  <br/> | <br/> |Se reciben datos de secuencia del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de secuencia desde el autor de la llamada al destinatario de la llamada.  <br/> 0 indica que la dirección de secuencia desde el destinatario de la llamada al autor de la llamada.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo que la llamada estuvo en un estado de congestión pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante el cual la congestión estuvo causada por la llegada retrasada de paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje de tiempo cuando la llamada estuvo compitiendo por recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Cantidad mínima de ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Cantidad máxima de ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desviación estándar de la estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||La cantidad promedio de ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Porcentaje de la llamada donde el extremo determinó que la conexión de red no pudo admitir el vídeo multiview.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densidad de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Tasa a la que se perdieron paquetes de vídeo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Cantidad promedio de ancho de banda asignado para vídeo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Externa  <br/> |Tipo de códecs de vídeo usados por el remitente. Consulte la [tabla CodecDescription](codecdescription.md) para obtener más información. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Ancho de resolución usado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Altura de resolución usada por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Número medio de transmisión de velocidad de fotogramas de vídeo usada por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Velocidad de bits máxima para el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Velocidad de bits Media para el remitente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Número máximo de secuencias de vídeo usada por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Externa  <br/> |Códigos de vídeo usados por el receptor. Consulte la [tabla CodecDescription](codecdescription.md) para obtener más información. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Ancho de resolución usada por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Altura de resolución usada por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Velocidad de fotogramas de vídeo Media usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Velocidad de bits máxima para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Velocidad de bits Media para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Secuencias de vídeo máximas para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Secuencias de vídeo mínimas para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modo de vídeo (por ejemplo, Galería o secuencia sencilla) para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Tasa de pérdida de paquetes después de que se ha aplicado la corrección de errores de reenvío.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Porcentaje de tiempo que estuvo activa la marca de capacidad dinámica.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |Char (9)  <br/> ||Resolución mínima medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de velocidad de bits baja (70 kilobits por segundo).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de velocidad de fotogramas baja (7,5 fotogramas por segundo, de entrada).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada que se produjo en la resolución más baja.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Longitud de la llamada en segundos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica si se han agregado los datos de varias llamadas.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

