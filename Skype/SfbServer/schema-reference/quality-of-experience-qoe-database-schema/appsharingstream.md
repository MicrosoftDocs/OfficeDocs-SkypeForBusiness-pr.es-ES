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
description: La tabla AppSharingStream contiene la métrica de calidad de la experiencia de las secuencias de red utilizadas para el uso compartido de aplicaciones. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: a10370814da5630a6d453b2ff4cad44b16b74ff1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="appsharingstream-table"></a>Tabla AppSharingStream
 
La tabla AppSharingStream contiene la métrica de calidad de la experiencia de las secuencias de red utilizadas para el uso compartido de aplicaciones. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |fecha y hora  <br/> |Principal, externa  <br/> |Fecha y hora en que se inició la sesión.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal, externa  <br/> |Identificador secuencial que se utiliza para distinguir entre las sesiones que se inicia en la misma fecha y al mismo tiempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, externa  <br/> |Representa el tipo de línea de vídeo utilizada en la llamada. Los valores permitidos son:  <br/> 0 - audio  <br/> 1 - vídeo  <br/> 2 - vídeo panorámica  <br/> 3 - aplicación o escritorio compartido  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Identificador único de la aplicación compartida de secuencia.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Vibración máxima detectado entre las llegadas de paquete RTP. (Vibración es una medida de la "inestabilidad" de una llamada). Valores de elevada vibración normalmente son causados por la congestión o un servidor sobrecargado multimedia y audio distorsionado o perdido como resultado.  <br/> |
|**Ida y vuelta** <br/> |int  <br/> ||Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Cantidad máxima de (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real viajar al otro extremo y volver. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Velocidad máxima de pérdida de paquetes de protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes RTP, un protocolo utilizado para la transmisión de audio y vídeo a través de Internet, no se ha podido llegar a su destino.) Tasas de pérdidas altas generalmente son causadas por la congestión; falta de ancho de banda; congestión inalámbrica o interferencia; o un servidor multimedia sobrecargado. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Número de paquetes enviados.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Estimado unidireccional ancho de banda disponible al final de la sesión. Se informó en bits por segundo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descripción de la aplicación de uso compartido de carga.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Promedio de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retardo entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Apariciones de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas unidireccional total. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración total de ráfagas unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Apariciones de la total separación unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad total brecha unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración total brecha unidireccional. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente continua; brechas indican retrasos entre estas ráfagas. Esta métrica mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**ApplicationSharingType** <br/> |varchar (256)  <br/> ||Tipo de contenido y la función de aplicación (que comparte o Visor).  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Tiempo total de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Un total superior equivale a un retardo mayor en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Promedio de tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Un total superior equivale a un retardo mayor en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Tiempo máximo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Un total superior equivale a un retardo mayor en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Las apariciones de ráfagas en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Duración en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos de ráfaga. Una transmisión "ráfagas" es una transmisión que los datos fluyen en ráfagas imprevisibles en contraposición a una corriente constante.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Repeticiones de separación en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos.  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densidad de separación en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Densidad baja brecha equivale a una mejor experiencia de visionado.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Duración de la brecha en el tiempo de procesamiento de protocolo de escritorio remoto (RDP) mosaicos. Duraciones de intervalo corto equivalen a una mejor experiencia de visionado.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Tasa total de mosaicos capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Velocidad promedio de cuadros capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Velocidad máxima de mosaicos capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |en t  <br/> ||Las apariciones de ráfaga en la velocidad de cuadros capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la velocidad de cuadros capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la velocidad de cuadros capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de la brecha en la velocidad de cuadros capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densidad de la brecha en la tasa de mosaicos capturados (en cuadros por segundo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Duración de la brecha en la velocidad de cuadros capturados (en cuadros por segundo).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Porcentaje total del contenido que no recibieron el visor pero se descartan y sobreescrito contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Porcentaje promedio del contenido que no recibieron el visor pero se descarta y sobrescrito por contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Porcentaje máximo del contenido que no recibieron el visor pero se descarta y sobrescrito por contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Ráfaga de repeticiones para el contenido que no recibieron el visor pero se descartan y sobrescriba contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Ráfaga de densidad para el contenido que no recibieron el visor pero se descartan y sobreescrito contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Ráfaga de duración para el contenido que no recibieron el visor pero se descartan y sobreescrito contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Apariciones de espacio para el contenido que no recibieron el visor pero se descartan y sobrescriba contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densidad de espacio para el contenido que no recibieron el visor pero se descartan y sobreescrito contenido fresco en su lugar.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Duración de espacio para el contenido que no recibieron el visor pero se descartan y sobreescrito contenido fresco en su lugar.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Número total de tramas rascado desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Promedio de tramas rascado desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Número máximo de fotogramas rascado desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Las apariciones de ráfaga en los marcos raspados desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en los marcos raspados desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en los marcos raspados desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Apariciones de brechas en los marcos raspadas desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de GAP en los marcos rascado desde el origen de los gráficos.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Duración de la brecha en las tramas rascado desde el origen de los gráficos.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Total velocidad entrantes recibidos por el Visor.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Promedio de velocidad entrantes recibidos por el Visor.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Entrada máxima mosaico tasa como recibidas por el Visor.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Ráfaga apariciones en la velocidad de entrada de azulejo como recibida por el Visor.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la velocidad de entrada de mosaico como recibida por el Visor.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la velocidad de entrada de mosaico como recibida por el Visor.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Apariciones de la brecha en la tasa de mosaico entrantes que se reciben por el Visor.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densidad de brechas en la tasa de mosaico entrantes que se reciben por el Visor.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Duración de la brecha en la velocidad de entrada de mosaico que se reciben por el Visor.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Total velocidad entrantes recibidos por el Visor.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Promedio de velocidad entrantes recibidos por el Visor.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Máxima velocidad de fotogramas entrantes que se reciben por el Visor.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ráfaga apariciones en la velocidad de fotogramas de entrada recibidos por el Visor.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la velocidad de fotogramas de entrada como recibida por el Visor.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la velocidad de fotogramas de entrada como recibida por el Visor.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de brechas en la velocidad de fotogramas entrantes que se reciben por el Visor.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de brechas en la velocidad de fotogramas entrantes que se reciben por el Visor.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Duración de la brecha en la velocidad de fotogramas entrantes que se reciben por el Visor.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Total tasa saliente de mosaico para el remitente.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Promedio tasa saliente de mosaico para el remitente.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Máxima velocidad de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Apariciones de ráfaga en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de brecha en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densidad de la brecha en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Duración de la brecha en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Total tasa saliente de marco para el remitente.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||promedio tasa saliente de marco para el remitente.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Máxima velocidad de fotogramas saliente para el remitente.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Separar las apariciones en la velocidad de fotogramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la velocidad de fotogramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la velocidad de fotogramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de brechas en la velocidad de fotogramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de la brecha en la velocidad de fotogramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Duración de la brecha en la velocidad de fotogramas de salida para el remitente.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Resolución de vídeo de medio alto, en píxeles.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Resolución de vídeo de medio ancho, en píxeles.  <br/> |
|**De entrada** <br/> |bit  <br/> ||Velocidad de fotogramas Media (en fotogramas por segundo) para las transmisiones entrantes.  <br/> |
|**Salida** <br/> |bit  <br/> ||Velocidad de fotogramas Media (en fotogramas por segundo) para las transmisiones salientes.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 significa que la dirección de flujo es desde el llamador al destinatario de la llamada.  <br/> 0 significa que la dirección de flujo es del destinatario de la llamada al llamador.  <br/> |
   

