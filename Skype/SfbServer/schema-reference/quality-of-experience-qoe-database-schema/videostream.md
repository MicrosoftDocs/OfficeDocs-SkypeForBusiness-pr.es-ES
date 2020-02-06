---
title: Tabla VideoStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Cada registro representa una secuencia de vídeo. Una línea de medios de vídeo suele contener dos secuencias de vídeo.
ms.openlocfilehash: 7eca8335ccf6905d3f80dd6ad8a5ccf00b749b39
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804240"
---
# <a name="videostream-table"></a>Tabla VideoStream
 
Cada registro representa una secuencia de vídeo. Una línea de medios de vídeo suele contener dos secuencias de vídeo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R al que hace referencia la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |IDENTIFICADOR exclusivo dentro de una línea de medios.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Externo, principal  <br/> |Descripción de la carga. Para obtener más información, consulte la [tabla PayloadDescription](payloaddescription.md) . <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Vibración máxima de red durante la sesión de video.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tiempo máximo de ida y vuelta para la secuencia de vídeo.  <br/> |
|**PacketLossRate** <br/> |decimal (4,5)  <br/> | <br/> |Tasa promedio de pérdida de paquetes durante la llamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal (4,5)  <br/> | <br/> |Pérdida máxima de paquetes observadas durante la llamada.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).  <br/> |
|**Ancho de banda más** <br/> |int  <br/> | <br/> |Cálculo de ancho de banda para la secuencia de vídeo.  <br/> |
|**Resolución de la** <br/> |carácter (9)  <br/> | <br/> |Resolución del vídeo en píxeles ancho multiplicado por píxeles alto. Se ha notificado como una cadena.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Promedio de velocidad de bits de la secuencia de vídeo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal (9, 4)  <br/> | <br/> |La velocidad de fotogramas de vídeo recibida.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal (9, 4)  <br/> | <br/> |La velocidad de fotogramas de vídeo enviada.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |La máxima tasa de bits de vídeo durante la sesión de video.  <br/> |
|**VideoFrameLossRate** <br/> |decimal (9, 4)  <br/> | <br/> |El porcentaje de fotogramas de video totales que se pierden.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |No disponible.  <br/> |
|**Media** <br/> |decimal (9, 4)  <br/> ||El porcentaje de fotogramas de video totales que se pierden.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que se encontraba en la resolución de formato de intercambio común (CIF).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que se mostraba en la resolución VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||El porcentaje de la llamada que se encontraba en la resolución de HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada sin colocación de fotogramas.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada con la caída de fotograma B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada con fotograma de fotograma BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada con el fotograma BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Porcentaje de la duración de la llamada con el fotograma BPSPI.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Se reciben los datos de la secuencia del lado del destinatario.  <br/> |
|**Saliente** <br/> |bit  <br/> | <br/> |Se reciben los datos de la secuencia en el lado del remitente.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.  <br/> 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la hora en que la llamada se encontraba en un estado de congestión de pérdida.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica el porcentaje de la llamada durante el cual la congestión fue causada por la llegada demorada de los paquetes de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica el porcentaje de la hora en que la llamada compite en los recursos de red.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Cantidad mínima de estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Cantidad máxima de estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desviación estándar de la estimación del ancho de banda medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Cantidad promedio de estimación del ancho de banda medido durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Porcentaje de la llamada en la que el punto de conexión determinó que la conexión de red no pudo admitir el vídeo de vista.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de repeticiones de ráfagas unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densidad de ráfaga unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Total de duración de ráfaga unidireccional. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de repeticiones de intervalos unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad de brechas en un camino total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración del intervalo unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**Tasa** <br/> |decimal (9, 4)  <br/> ||Velocidad a la que se han perdido paquetes de video.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Cantidad promedio de ancho de banda asignado para el vídeo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Extranjero  <br/> |Tipo de códecs de vídeo usados por el remitente. Para obtener más información, consulte la [tabla CodecDescription](codecdescription.md) . <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Ancho de resolución usado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Alto de resolución usado por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Promedio de transmisión de velocidad de fotogramas de vídeo utilizada por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||La tasa de bits máxima para el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Promedio de velocidad de bits del remitente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Número máximo de transmisiones de vídeo usadas por el remitente.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Extranjero  <br/> |Códigos de vídeo usados por el destinatario. Para obtener más información, consulte la [tabla CodecDescription](codecdescription.md) . <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Ancho de resolución usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Alto de resolución usado por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**Media** <br/> |float  <br/> ||Promedio de velocidad de fotogramas de video usada por el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||La velocidad de bits máxima para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Promedio de velocidad de bits para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Máximo de transmisiones de vídeo para el destinatario.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Las transmisiones de video mínimas para el destinatario.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modo de vídeo (por ejemplo, Galería o un único flujo) para el receptor.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**Tasa** <br/> |float  <br/> ||Tasa de pérdida de paquetes después de aplicar la corrección de errores de reenvío.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**Porcentaje** <br/> |float  <br/> ||Porcentaje de tiempo que el indicador de capacidad dinámica estaba activo.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |carácter (9)  <br/> ||Resolución mínima medida durante la llamada.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de baja velocidad de bits (70 kilobits por segundo).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**Porcentaje** <br/> |float  <br/> ||Porcentaje de la llamada por debajo del umbral de baja velocidad de fotogramas (7,5 fotogramas por segundo, entrada).  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**Porcentaje** <br/> |float  <br/> ||Porcentaje de la llamada que se produjo en la resolución más baja.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Duración de la llamada en segundos.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica si los datos se han agregado desde varias llamadas.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

