---
title: Tabla AppSharingStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: La tabla AppSharingStream contiene métricas de experiencia de calidad para las secuencias de red que se usan para compartir aplicaciones. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 61606f204310b3956eb74bd19d0c9d8d421e7818
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295122"
---
# <a name="appsharingstream-table"></a>Tabla AppSharingStream
 
La tabla AppSharingStream contiene métricas de experiencia de calidad para las secuencias de red que se usan para compartir aplicaciones. Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Fechas  <br/> |Principal, extranjero  <br/> |Fecha y hora en que comenzó la sesión.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal, extranjero  <br/> |Identificador secuencial que se usa para diferenciar las sesiones que comenzaron en la misma fecha y al mismo tiempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal, extranjero  <br/> | Consulte la [tabla MediaLine](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Identificador único de la secuencia de uso compartido de aplicaciones.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Valor medio de las vibraciones detectadas entre la llagada de paquetes RTP. (La vibración es una forma de medir la "inestabilidad" de una llamada). Los valores altos de vibración suelen deberse a la congestión o a una sobrecarga del servidor multimedia y dan lugar a la distorsión o pérdida del audio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Vibración máxima detectada entre las llegadas al paquete RTP. (La vibración es una medida de la "irregularidad" de una llamada.) Los valores de vibración elevada suelen estar causados por una congestión o un servidor multimedia sobrecargado y tienen como resultado una distorsión o pérdida de audio.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Tiempo medio (en milisegundos) necesario para que un paquete de protocolo de transporte en tiempo real (RTP) llegue a otro extremo y vuelva. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Cantidad máxima de (en milisegundos) necesaria para que un paquete de protocolo de transporte en tiempo real viaje a otro extremo y después de nuevo. Los tiempos de ida y vuelta de 200 milisegundos o menos se consideran de calidad aceptable.  <br/> Los valores elevados en los tiempos del recorrido de ida y vuelta pueden deberse a que se trata de enrutamientos de llamadas internacionales, una configuración incorrecta del enrutamiento o a la sobrecarga en el servidor de medios y causan dificultades en las conversaciones de audio en tiempo real bidireccionales.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Tasa media de pérdida de paquetes RTP (se habla de pérdida de paquetes cuando los paquetes RTP, un protocolo utilizado para transmitir audio y vídeo a través de Internet, no llegan a su destino). Una tasa alta de pérdida se suele deber a la congestión, falta de ancho de banda, congestión o interferencias en una conexión inalámbrica o la sobrecarga de un servidor de medios. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Tasa máxima de pérdida de paquetes del Protocolo de transporte en tiempo real (RTP). (La pérdida de paquetes se produce cuando los paquetes RTP, un protocolo usado para transmitir audio y vídeo a través de Internet, no pudo alcanzar su destino). Las tarifas de pérdida elevada suelen ser causadas por la congestión; falta de ancho de banda; disgestión o interferencias inalámbricas; o un servidor multimedia sobrecargado. Generalmente, la pérdida de paquetes da lugar a la pérdida o la distorsión del audio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Número de paquetes enviados.  <br/> |
|**Ancho de banda más** <br/> |int  <br/> ||Ancho de banda de unidireccional Estimado disponible al final de la sesión. Se notifica en bits por segundo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descripción de la carga de uso compartido de aplicaciones.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Cantidad total de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Cantidad promedio de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Cantidad máxima de latencia unidireccional. Latencia unidireccional relativa mide el retraso entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de repeticiones de ráfagas unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Total de duración de ráfaga unidireccional. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de repeticiones de intervalos unidireccionales. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidad de brechas en un camino total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duración del intervalo unidireccional total. Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante; los huecos indican retrasos entre estas ráfagas. Esta medida mide el flujo de datos entre el cliente y el servidor.  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)  <br/> ||Función de aplicación (persona que comparte o visor) y tipo de contenido.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Tiempo total de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP). Un total más alto iguala a un retraso más largo en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Tiempo promedio de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP). Un total más alto iguala a un retraso más largo en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Tiempo máximo de procesamiento para los mosaicos del Protocolo de escritorio remoto (RDP). Un total más alto iguala a un retraso más largo en la experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Duración de ráfagas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Una transmisión "por ráfagas" es una transmisión en la que los datos fluyen en ráfagas imprevisibles en lugar de un flujo constante.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Repeticiones de huecos en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densidad de brechas en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). La densidad de huecos bajos corresponde a una mejor experiencia de visualización.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Duración del hueco en el tiempo de procesamiento de los mosaicos del Protocolo de escritorio remoto (RDP). Las duraciones cortas equivalen a una mejor experiencia de visualización.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Tasa total de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Velocidad promedio de los mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Frecuencia máxima de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |en t  <br/> ||Repeticiones de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la tasa de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de huecos en la tasa de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densidad de huecos en la tasa de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Duración del hueco en la tasa de mosaicos capturados (en mosaicos por segundo).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Porcentaje total del contenido que no se ha podido alcanzar con el visor, pero que se ha descartado y ha sido reemplazado por contenido nuevo.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Porcentaje medio del contenido que no se ha encontrado en el visor pero que se ha descartado y se ha reemplazado por contenido nuevo.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Porcentaje máximo del contenido que no se ha podido alcanzar con el visor, pero que se descartó y se sobrescribió por contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas para el contenido que no se ha podido alcanzar con el visor, pero que se han descartado y reemplazado por contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga para el contenido que no se ha podido alcanzar con el visor, pero se ha descartado y ha sido reemplazado por contenido nuevo.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Duración de ráfaga para el contenido que no se ha podido alcanzar con el visor, pero se ha descartado y ha sido reemplazado por contenido nuevo.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Las repeticiones de huecos para el contenido que no se ha podido alcanzar con el visor pero se han descartado y reemplazado por contenido nuevo.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densidad de brechas para el contenido que no se ha podido alcanzar con el visor, pero que se descartó y sobrescribe por contenido nuevo.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||El intervalo de tiempo para el contenido que no se ha podido alcanzar con el visor, se ha descartado y ha sido reemplazado por contenido nuevo.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Número total de fotogramas descartados de la fuente de gráficos.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Número promedio de fotogramas descartados del origen de gráficos.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Número máximo de fotogramas descartados del origen de gráficos.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en los fotogramas descartados de la fuente de gráficos.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en las tramas descartadas de la fuente de gráficos.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en las tramas descartadas del origen de gráficos.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de huecos en los fotogramas descartados del origen de los gráficos.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de huecos en los fotogramas descartados del origen de gráficos.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Duración del hueco en los fotogramas descartados del origen de los gráficos.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Total de la velocidad de fotogramas entrantes recibida por el visor.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Promedio de velocidad de fotogramas entrante recibida por el visor.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Cantidad máxima de mosaico entrante recibida por el visor.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfaga en la tasa de mosaico entrante recibida por el visor.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la tasa de icono entrante recibida por el visor.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la tasa de mosaico entrante recibida por el visor.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Las repeticiones de huecos de la velocidad de los mosaicos entrantes recibidas por el visor.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densidad de hueco en la tasa de mosaico entrante recibida por el visor.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Duración del intervalo en la tasa de mosaico entrante recibida por el visor.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Total de la velocidad de fotogramas entrantes recibida por el visor.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Promedio de velocidad de fotogramas entrante recibida por el visor.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Cantidad máxima de fotogramas entrantes recibida por el visor.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en la velocidad de fotogramas entrantes recibidas por el visor.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la velocidad de fotogramas entrantes recibida por el visor.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||La duración de la ráfaga en la velocidad de fotogramas entrante recibida por el visor.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Las repeticiones de huecos de la velocidad de fotogramas entrantes recibidas por el visor.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de huecos en la velocidad de fotogramas entrante recibida por el visor.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Duración del hueco en la velocidad de fotogramas entrante que recibió el visor.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Intervalo total de los mosaicos salientes del remitente.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Promedio de la velocidad de los iconos salientes del remitente.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Velocidad máxima de los iconos salientes del remitente.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfaga en la tasa del mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfaga en la tasa del mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la tasa del mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de huecos en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densidad de hueco en la tasa de mosaico saliente para el remitente.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Duración del hueco en la tasa del mosaico saliente para el remitente.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Total de la velocidad de los fotogramas salientes del remitente.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||promedio de velocidad de fotograma saliente para el remitente.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Velocidad máxima de los fotogramas salientes del remitente.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Repeticiones de ráfagas en la velocidad de fotogramas salientes del remitente.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densidad de ráfagas en la velocidad de fotogramas salientes del remitente.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Duración de ráfaga en la velocidad de fotogramas salientes del remitente.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Repeticiones de huecos en la velocidad de fotogramas salientes del remitente.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densidad de huecos en la velocidad de fotogramas salientes del remitente.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Duración del hueco en la velocidad de fotogramas salientes del remitente.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Promedio de altura de la resolución de video, en píxeles.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Promedio de ancho de resolución de video, en píxeles.  <br/> |
|**Entrada** <br/> |bit  <br/> ||Promedio de velocidad de fotogramas (en fotogramas por segundo) para transfronterizas entrantes.  <br/> |
|**Saliente** <br/> |bit  <br/> ||Promedio de velocidad de fotogramas (en fotogramas por segundo) para transfronterizas salientes.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.  <br/> 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.  <br/> |
   

