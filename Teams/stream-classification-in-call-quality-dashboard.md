---
title: Clasificación de la transmisión en el panel de calidad de llamadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Descubra cómo se clasifica la calidad de la transmisión en el panel de calidad de llamadas para Microsoft Teams y Skype for Business Online.
ms.openlocfilehash: ad18b15019ed82d629a4c32c27544d052cd2bc92
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298635"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Clasificación de la transmisión en el panel de calidad de llamadas

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definiciones del clasificador

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>Clasificador de audio

Una transmisión de audio se marca como mala si se cumplen una o más de las condiciones siguientes:

|**Métrica**|**Condición**|**Explicación**|
|:-----|:-----|:-----|
|Audio Degradation Avg|>1,0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|>500|Tiempo medio de ida y vuelta en la propagación de red que se calcula como se especifica en RFC3550 en milisegundos.|
|Packet Loss Rate|>0,1|Porcentaje medio de pérdida de paquetes en la transmisión.|
|Vibración|>30|Vibración media producida en la transmisión en milisegundos.|
|Ratio Concealed Samples Avg|> 0,07|Relación media entre el número de marcos de audio con muestras ocultas generada por la recuperación de pérdida de paquetes para el número total de marcos de audio.|

### <a name="video-classifier"></a>Clasificador de vídeo

Una transmisión de vídeo se marca como buena o mala según el valor de la primera métrica disponible, en el orden siguiente:

|**Paso n. º**|**Métrica**|**Condición**|**Clasificación si la condición es verdadera**|**Clasificación si la condición es falsa**|**Clasificación si la métrica no está disponible**|**Explicación**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Continúe con el paso 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 7|Poor|Good|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|La tasa de pérdida de paquetes después de que se haya aplicado FEC en todas las transmisiones y códecs de vídeo.|

### <a name="vbss-classifier"></a>Clasificador de VBSS

Una transmisión de VBSS se marca como buena o mala según el valor de la primera métrica disponible, en el orden siguiente:

|**Paso N. º**|**Métrica**|**Condición**|**Clasificación si la condición es verdadera**|**Clasificación si la condición es falsa**|**Clasificación si la métrica no está disponible**|**Explicación**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Continúe con el paso 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|<2|Poor|Good|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|>  0.15|Poor|Good|Unclassified|La tasa de pérdida de paquetes después de que se haya aplicado FEC en todas las transmisiones y códecs de vídeo.|

### <a name="application-sharing-classifier"></a>Clasificador de uso compartido de aplicaciones

Una transmisión de uso compartido de aplicaciones se marca como mala si se cumplen una o más de las condiciones siguientes:


| **Métrica**                                     | **Condición** | **Explicación**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | > 36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | > 400         | Latencia media en milisegundos en el procesamiento de ventanas en la pila de RDP del servidor de conferencias.                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1,75        | Promedio de retraso relativo promedio entre los puntos de conexión en segundos para las transmisiones de uso compartido de aplicaciones.                                                                                                                       |

## <a name="unclassified-streams"></a>Transmisiones sin clasificar

En el panel de calidad de llamadas, una transmisión se marca como sin clasificar cuando falla la conectividad de ICE o cuando no se notifican todas las métricas necesarias para calcular la clasificación de la transmisión.

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> Se pueden usar la dimensión "Utilización de paquetes" y la medición "Uso medio de paquetes" para determinar la actividad de paquetes de una transmisión.


## <a name="related-topics"></a>Temas relacionados
[Activar y usar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)
