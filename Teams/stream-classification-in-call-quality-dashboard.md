---
title: Clasificación de transmisiones en el panel de calidad de llamadas
ms.author: serdars
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Obtenga información sobre cómo se clasifica la calidad de la transmisión en el panel de calidad de llamadas (CQD) para Microsoft Teams y Skype Empresarial Online.
ms.openlocfilehash: 400dcd953805595b4457b4ca9443c31b66f7425d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909044"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Clasificación de transmisiones en el panel de calidad de llamadas (CQD)

El panel de calidad de llamadas (CQD) para Microsoft Teams y Skype Empresarial Online le permite obtener información sobre la calidad de las llamadas que se realizan con los servicios de Microsoft Teams y Skype Empresarial. Este tema proporciona información detallada sobre la clasificación de calidad de las transmisiones multimedia. Para obtener más información sobre el CQD y cómo configurarlo, consulte [Configurar panel de calidad de llamadas.](turning-on-and-using-call-quality-dashboard.md)

## <a name="classifier-definitions"></a>Definiciones del clasificador

Las transmisiones del CQD se clasifican como _Buenas,_ Malas o _Sin_ clasificar en función de los valores de las métricas de calidad clave disponibles. Las métricas y condiciones usadas para clasificar la transmisión se muestran en las tablas siguientes. Las dimensiones "Debido a" del CQD se pueden usar para comprender qué métrica es la responsable de una _clasificación de_ mala. Para obtener más información sobre estas dimensiones, vea dimensiones y medidas disponibles [en el panel de calidad de llamadas.](dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="audio-classifier"></a>Clasificador de audio

Si se cumplen una o varias de las condiciones siguientes, una transmisión de audio se marca como _mala:_

|Métrica|Escenario|Condición|Explicación|
|:-----|:-----|:-----|:-----|
|Audio Degradation Avg|La descripción de carga no es LAR|>1,0|Media de degradación de la puntuación de opinión media de la red en la transmisión. Cuánta vibración y pérdida de red ha afectado a la calidad del audio recibido.|
|Round Trip|ALL|>500|Tiempo medio de propagación de red de ida y vuelta, calculado en milisegundos. Detalles disponibles en [RFC3550.](https://tools.ietf.org/html/rfc3550)|
|Packet Loss Rate|ALL|>0,1|Porcentaje medio de pérdida de paquetes en la transmisión.|
|Vibración|ALL|>30|Vibración media producida en la transmisión en milisegundos.|
|Ratio Concealed Samples Avg|La descripción de carga no es LAR|> 0,07|Relación media entre el número de tramas de audio con muestras ocultas generadas por la pérdida de paquetes y el número total de tramas de audio.|
||||

### <a name="video-classifier-due-to-freeze"></a>Clasificador de vídeo debido a inmovilización

La transmisión de vídeo  se marca _como_ Buena o Mala en función del valor de una puntuación clasificador generada para estimar que el usuario final experimentó vídeo inmovilizado. Este clasificador solo está disponible para el producto de Microsoft Teams.

|Paso N. º|Métrica|Escenario|Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0,246|_Poor_|_Good_|_Unclassified_|Puntuación entre 0 y 1 generada en función de una combinación de experiencia de usuario, inmovilizar estadísticas de duración y experiencia de llamada general |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0,524|_Poor_|_Good_|_Unclassified_|Puntuación entre 0 y 1 generada en función de una combinación de experiencia de usuario, inmovilizar estadísticas de duración y experiencia de llamada general |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Clasificador de vídeo
Una transmisión de vídeo se marca como _buena_ _o_ mala en función del valor de la primera métrica disponible en el siguiente orden:

|Paso N. º|Métrica|Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Continúe con el paso 2|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. El promedio incluye fotogramas que se recuperan de pérdidas de red.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|>  0.15|_Poor_|_Good_|_Unclassified_|Porcentaje de pérdida de paquetes tras aplicar fec en todas las transmisiones de vídeo y los códecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Clasificador de VBSS

Una transmisión en secuencias  de  VBSS se marca como buena o mala en función del valor de la primera métrica disponible en el siguiente orden:

|Paso N. º |Métrica |Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Continúe con el paso 2|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. El promedio incluye fotogramas que se recuperan de pérdidas de red.|
|2|Video Frame Rate Avg|<2|_Poor_|_Good_|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|>  0.15|_Poor_|_Good_|_Unclassified_|Porcentaje de pérdida de paquetes tras aplicar fec en todas las transmisiones de vídeo y los códecs.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Clasificador de uso compartido de aplicaciones

Una secuencia de uso compartido de aplicaciones se marca como _mala_ si se cumplen una o varias de las condiciones siguientes:

| Métrica     | Condición | Explicación |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Porcentaje de ventanas que se descartan en lugar de enviarse a un equipo remoto (por ejemplo, del MCU a un visor). Las ventanas descartadas (o mínimas) pueden deberse a restricciones en el ancho de banda entre el cliente y el servidor. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latencia media en milisegundos en el procesamiento de ventanas en la pila de RDP del servidor de conferencias. |
| AppSharing Relative OneWay Average | > 1,75 | Retraso medio relativo un solo sentido entre los puntos de conexión en segundos durante las transmisiones con uso compartido de aplicaciones. |
| | | |

## <a name="unclassified-streams"></a>Transmisiones sin clasificar

En el CQD, una transmisión se marca como _Unclassified_ cuando se produce un error en la conectividad del establecimiento de conectividad interactiva (ICE) o cuando no se notifican todas las métricas necesarias para calcular la clasificación de la transmisión.

Para verificar los errores de conectividad de ICE, examine las dimensiones "ICE de primera conectividad" e "ICE de segunda conectividad" para obtener un valor "FALLO". Si alguno de los valores indica un error, la transmisión se marca como _Unclassified._

Si la conectividad de ICE ha tenido éxito en una transmisión _sin_ clasificar, es probable que la transmisión se considere _unclassified_ porque no se han notificado métricas de transmisiones clave. Hay algunas razones por las que puede que no se notifiquen estas métricas:

- **No se han recibido informes de QoE:** las métricas usadas para la clasificación se notifican en un informe de QoE enviado al final de una llamada. Si este informe no se genera (por ejemplo, porque es posible que algunos puntos de conexión de terceros no envíen QoE) o no se pueda enviar (por ejemplo, debido a una interrupción de la red), el CQD no puede clasificar la transmisión.

  > [!TIP]
  > La dimensión "Registro QoE disponible" se puede usar para determinar si se ha recibido un informe QoE para una transmisión. Tenga en cuenta que esta dimensión tendrá un valor de "True" si se ha recibido un informe QoE desde cualquier punto de conexión. Se requiere un informe QoE de ambos puntos de conexión para obtener el informe más preciso de las métricas.

- **Llamadas cortas:** es posible que las llamadas cortas no tengan suficiente actividad multimedia para calcular métricas de transmisiones clave. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.

  > [!TIP]
  > Se pueden usar las dimensiones "Duración (segundos)", "Duración (minutos)", "Duración de 5 segundos o menos" y "Duración de 60 segundos o más" para determinar la duración de una transmisión. También se puede usar la medición "Duración media de la llamada" para calcular la duración media de un conjunto de transmisiones.

- **Uso bajo de paquetes:** como en el escenario de "llamada corta", se requiere un uso suficiente de paquetes para calcular las métricas de flujo clave. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.
  - Un escenario común de uso bajo de paquetes se produce cuando un asistente se une a una reunión para escuchar al moderador, pero nunca habla (el micrófono está silenciado durante la mayor parte de la llamada). Aquí, la transmisión de audio entrante al cliente tiene un alto uso de paquetes, mientras que la transmisión de audio saliente desde el cliente tiene poco o ningún uso de paquetes. La duración de la transmisión puede ser de una hora o más, pero el uso de paquetes en la transmisión desde el cliente al servidor es bajo ya que el micrófono se ha silenciado y se produce una transmisión _sin_ clasificar.

  > [!TIP]
  > Se pueden usar la dimensión "Utilización de paquetes" y la medición "Uso medio de paquetes" para determinar la actividad de paquetes de una transmisión.

## <a name="related-topics"></a>Temas relacionados
[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilino y de edificio](CQD-upload-tenant-building-data.md)

[Informes y datos del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
