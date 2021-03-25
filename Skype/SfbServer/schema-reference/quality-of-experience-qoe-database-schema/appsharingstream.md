---
title: Tabla AppSharingStream
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
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La tabla AppSharingStream contiene métricas de calidad de la experiencia de los flujos de red utilizados para el uso compartido de las aplicaciones. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d95e0d78175f8e17363dc558d82cafefba36ce28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120882"
---
# <a name="appsharingstream-table"></a>Tabla AppSharingStream
 
La tabla AppSharingStream contiene métricas de calidad de la experiencia de los flujos de red utilizados para el uso compartido de las aplicaciones. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Principal, Exterior  <br/> |Fecha y hora en que se inició la sesión.  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal, Exterior  <br/> |Identificador secuencial usado para distinguir las sesiones que se iniciaron en la misma fecha de las que se iniciaron a la misma hora.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, Externa  <br/> | Consulte [Tabla MediaLine](./medialine-0.md). <br/> |
|**StreamID** <br/> |Entero  <br/> |Principal  <br/> |Identificador único del flujo de uso compartido de aplicaciones.  <br/> |
|**JitterInterArrival** <br/> |Entero  <br/> ||Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**JitterInterArrivalMax** <br/> |Entero  <br/> ||Valor máximo de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**RoundTrip** <br/> |Entero  <br/> ||Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**RoundTripMax** <br/> |Entero  <br/> ||Tiempo máximo (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Tasa máxima de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketUtilization** <br/> |Entero  <br/> ||Número de paquetes enviados.  <br/> |
|**BandwidthEst** <br/> |Entero  <br/> ||Ancho de banda unilateral estimado disponible al final de la sesión. Se muestra en bits por segundo.  <br/> |
|**AppSharingPayloadDescription** <br/> |Entero  <br/> ||Descripción de la aplicación que comparte la carga.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad media de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. La latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |Entero  <br/> ||Cantidad total de ráfagas unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad total de ráfagas unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duración total de ráfagas unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |Entero  <br/> ||Cantidad total de intervalos unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad total de intervalos unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración total de intervalos unidireccionales. Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable; las diferencias indican retrasos entre estas ráfagas. Esta métrica mide el modo en que los datos fluyen entre el cliente y el servidor.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Rol de aplicación (aplicación que comparte o visualiza) y tipo de contenido.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Tiempo de procesamiento total de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Tiempo de procesamiento de promedio de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Tiempo de procesamiento máximo de datos de protocolo de escritorio remoto (RDP). Un total elevado indica un mayor retraso en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |Entero  <br/> ||Repeticiones de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una transmisión "ráfaga" es una transmisión en la que los datos fluyen en ráfagas impredecibles en lugar de una secuencia estable.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |Entero  <br/> ||Repeticiones de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densidad de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una densidad de intervalos baja indica una experiencia de visualización de mayor calidad.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Duración de intervalos en el tiempo de procesamiento de datos de protocolo de escritorio remoto (RDP). Una duración de intervalos corta indica una experiencia de visualización de mayor calidad.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Tasa total de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Tasa media de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Tasa máxima de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |Entero  <br/> ||Repeticiones de intervalos en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos en la tasa de datos capturados (en datos por segundo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Duración de intervalos en la tasa de datos capturados (en datos por segundo).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Porcentaje total de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Porcentaje medio de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Porcentaje máximo de contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |Entero  <br/> ||Repeticiones de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |Entero  <br/> ||Repeticiones de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densidad de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Duración de intervalos en el contenido que no llega al visor descartado y sobrescrito con contenido nuevo.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Número total de marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Número medio de marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Número máximo de marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |Entero  <br/> ||Repeticiones de ráfagas en los marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en los marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en los marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |Entero  <br/> ||Intervalos de ráfagas en los marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de ráfagas en los marcos descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Duración de ráfagas en los marcos descartados del origen de los gráficos.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Tasa de tramas de entrada total recibidas por el visor.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Tasa de tramas de entrada de promedio recibidas por el visor.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Tasa de datos de entrada máxima recibidos por el visor.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |Entero  <br/> ||Repeticiones de ráfagas de la tasa de datos de entrada recibidos por el visor.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas de la tasa de datos de entrada recibidos por el visor.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas de la tasa de datos de entrada recibidos por el visor.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |Entero  <br/> ||Repetición de intervalos de la tasa de datos de entrada recibidos por el visor.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos de la tasa de datos de entrada recibidos por el visor.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Duración de intervalos de la tasa de datos de entrada recibidos por el visor.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Tasa de tramas de entrada total recibidas por el visor.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Tasa de tramas de entrada de promedio recibidas por el visor.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Tasa de tramas de entrada máxima recibidas por el visor.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |Entero  <br/> ||Repeticiones de ráfagas de la tasa de tramas de entrada recibidas por el visor.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas de la tasa de tramas de entrada recibidas por el visor.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas de la tasa de tramas de entrada recibidas por el visor.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |Entero  <br/> ||Repeticiones de intervalos de la tasa de tramas de entrada recibidas por el visor.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos de la tasa de tramas de entrada recibidas por el visor.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Duración de intervalos de la tasa de tramas de entrada recibidas por el visor.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Tasa de datos de salida total para el remitente.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Tasa de datos de salida de promedio para el remitente.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Tasa de datos de salida máxima para el remitente.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |Entero  <br/> ||Repeticiones de ráfagas en la tasa de datos de salida para el remitente.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de datos de salida para el remitente.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de datos de salida para el remitente.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |Entero  <br/> ||Repeticiones de intervalos en la tasa de datos de salida para el remitente.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos en la tasa de datos de salida para el remitente.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Duración de intervalos en la tasa de datos de salida para el remitente.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Tasa de tramas de salida total para el remitente.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||Tasa de tramas de salida de promedio para el remitente.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Tasa de tramas de salida máxima para el remitente.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |Entero  <br/> ||Repeticiones de ráfagas en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |Entero  <br/> ||Repeticiones de intervalos en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de intervalos en la tasa de tramas de salida para el remitente.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Duración de intervalos en la tasa de tramas de salida para el remitente.  <br/> |
|**AverageRectangleHeight** <br/> |Entero  <br/> ||Promedio de altura de resolución de vídeo en píxeles.  <br/> |
|**AverageRectangleWidth** <br/> |Entero  <br/> ||Promedio de anchura de resolución de vídeo en píxeles.  <br/> |
|**Entrada** <br/> |bit  <br/> ||Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de entrada.  <br/> |
|**Saliente** <br/> |bit  <br/> ||Tasa de tramas de promedio (en tramas por segundo) para las transmisiones de salida.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 significa que la dirección de la secuencia va desde el autor de la llamada hasta el destinatario.  <br/> 0 indica que la dirección de la secuencia va del destinatario de la llamada al autor de la llamada.  <br/> |
