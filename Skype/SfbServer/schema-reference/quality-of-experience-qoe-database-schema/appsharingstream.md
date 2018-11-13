---
title: Tabla AppSharingStream
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: En la tabla AppSharingStream contiene las métricas de calidad de la experiencia de las secuencias de red usadas para uso compartido de aplicaciones. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 4eeac3f7b082d4a798736bd9897b90668a1d44b2
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294306"
---
# <a name="appsharingstream-table"></a>Tabla AppSharingStream
 
En la tabla AppSharingStream contiene las métricas de calidad de la experiencia de las secuencias de red usadas para uso compartido de aplicaciones. En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |fecha y hora  <br/> |Principal, externa  <br/> |Fecha y hora en se inició la sesión.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal, externa  <br/> |Identificador secuencial usado para distinguir entre las sesiones que iniciar en la misma fecha y al mismo tiempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, externa  <br/> | Consulte la [Tabla MediaLine](https://docs.microsoft.com/en-us/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Identificador único de la aplicación de uso compartido de secuencia.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Vibración máxima detectado entre llegados de paquete RTP. (Vibración es una medida de la "inestabilidad" de una llamada). Los valores de vibración alta normalmente causados por la congestión o un servidor de medios sobrecargado y audio distorsionado o perdido como resultado.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Cantidad máxima de (en milisegundos) necesario para que viajar al otro extremo y, a continuación, hacer una copia de un paquete de protocolo de transporte en tiempo real. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Tasa máxima de pérdida de paquetes de protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes de RTP, un protocolo que se usa para la transmisión de audio y vídeo a través de Internet, no se pudo llegar a su destino.) Tasas de pérdidas alta generalmente causados por la congestión; falta de ancho de banda; congestión inalámbrica o interferencias; o un servidor de medios sobrecargado. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Número de paquetes enviados.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Estimado unidireccional ancho de banda disponible al final de la sesión. Indica en bits por segundo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descripción de la aplicación de uso compartido de carga.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración de intervalos unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable; carencias de indican los retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**ApplicationSharingType** <br/> |varchar (256)  <br/> ||Función de aplicación (que comparte o visualiza) y tipo de contenido.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Tiempo total de procesamiento de protocolo de escritorio remoto (RDP) se organizan en mosaico. Un total superior es igual a un retraso en la experiencia de visualización más largo.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Promedio de tiempo de procesamiento de protocolo de escritorio remoto (RDP de) mosaicos. Un total superior es igual a un retraso en la experiencia de visualización más largo.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Tiempo máximo de procesamiento de protocolo de escritorio remoto (RDP) se organizan en mosaico. Un total superior es igual a un retraso en la experiencia de visualización más largo.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Duración en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos de ráfagas. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una secuencia estable.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos.  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densidad de intervalos en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) se organizan en mosaico. Densidad de intervalos bajo equivale a una mejor experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Duración de intervalos en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) se organizan en mosaico. Las duraciones de espacio corto equivalen a una mejor experiencia de visualización.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Tasa total de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Velocidad media de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Tasa máxima de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |en t  <br/> ||Repeticiones de ráfagas en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Duración de intervalos en la tasa de datos capturados (en datos por segundo).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Porcentaje total de contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Porcentaje promedio de contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Porcentaje máximo de contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Ráfagas de repeticiones para el contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Ráfagas densidad para el contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Ráfagas de duración para el contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos en el contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densidad de intervalos en el contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Duración de intervalos en el contenido que no llega al visor pero descartado y sobrescrito con contenido nuevo.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Número total de marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Número medio de marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Número máximo de marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en los marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en los marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en los marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos en los marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos en los marcos descartados desde el origen de gráficos.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Duración de intervalos en los marcos descartados desde el origen de gráficos.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Total de la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Promedio de tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Tasa de datos de entrada máxima recibidos por el Visor.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en la tasa de datos entrantes recibidos por el Visor.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de datos entrantes recibidos por el Visor.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de datos entrantes recibidos por el Visor.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos de la tasa de datos entrantes recibidos por el Visor.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos de la tasa de datos entrantes recibidos por el Visor.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Duración de intervalos de la tasa de datos entrantes recibidos por el Visor.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Total de la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Promedio de tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Máxima velocidad de fotogramas entrantes recibidas por el Visor.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos de la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos de la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Duración de intervalos de la tasa de tramas de entrada recibidos por el Visor.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Total tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Promedio tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Máximo tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en la tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos en la tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos en la tasa de datos salientes para el remitente.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Duración de intervalos en la tasa de datos salientes para el remitente.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Total tasa de tramas salientes para el remitente.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||promedio tasa de tramas salientes para el remitente.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Máxima velocidad de fotogramas salientes para el remitente.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de intervalos en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Duración de intervalos en la tasa de tramas de salida para el remitente.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Promedio de altura de resolución de vídeo, en píxeles.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Promedio de ancho de resolución de vídeo, en píxeles.  <br/> |
|**De entrada** <br/> |bit  <br/> ||Velocidad de fotogramas Media (en tramas por segundo) para las transmisiones de entrada.  <br/> |
|**Saliente** <br/> |bit  <br/> ||Velocidad de fotogramas Media (en tramas por segundo) para las transmisiones salientes.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 significa que la dirección de secuencia desde el autor de la llamada al destinatario de la llamada.  <br/> 0 indica que la dirección de secuencia desde el destinatario de la llamada al autor de la llamada.  <br/> |
   

