---
title: Clasificación de transmisiones en el panel de calidad de llamadas (CQD)
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Obtenga información sobre cómo se clasifica la calidad de la transmisión en el Panel de calidad de llamadas para Microsoft Teams y Skype Empresarial en línea.
ms.openlocfilehash: 5ee2575cf952eb9d7e78f14b2b8ba7693cd3f878
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059261"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Clasificación de transmisiones en el panel de calidad de llamadas (CQD)

El Panel de calidad de llamadas (CQD) para Microsoft Teams y Skype Empresarial Online le permite obtener información sobre la calidad de las llamadas realizadas con los servicios de Microsoft Teams y Skype Empresarial. Este tema proporciona información detallada sobre la clasificación de calidad de las transmisiones multimedia. Para obtener más información sobre el CQD y cómo configurarlo, consulte [Configurar el panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definiciones del clasificador

Secuencias en el CQD se clasifican como _Buena_, _Mala_ o _Sin clasificar_ en función de los valores de las métricas de calidad clave disponibles. Las métricas y condiciones que se usan para clasificar la transmisión se muestran en las tablas siguientes. Las dimensiones del CQD "Poor Due To" se pueden usar para comprender qué métrica es responsable de una clasificación _de mala_ calidad. Para obtener más información sobre estas dimensiones, consulte [Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Clasificador de audio

Si se cumplen una o varias de las siguientes condiciones y el uso de paquetes se > 500 paquetes, una secuencia de audio se marca como _mala_:

|Métrica|Escenario|Condición|Explicación|
|:-----|:-----|:-----|:-----|
|Round Trip|TODO|>500|Tiempo medio de propagación de red de ida y vuelta, calculado en milisegundos. Detalles disponibles en [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|TODO|>0,1|Porcentaje medio de pérdida de paquetes en la transmisión.|
|Vibración|TODO|>30|Vibración media producida en la transmisión en milisegundos.|
||||

### <a name="video-classifier-due-to-freeze"></a>Clasificador de vídeo debido a bloqueo

La transmisión en secuencias de vídeo se marca  _como Buena_ o _Mala_ en función del valor de una puntuación de clasificador generada para calcular que el usuario final ha experimentado Frozen Video. Este clasificador solo está disponible para Microsoft Teams producto.

|Paso N. º|Métrica|Escenario|Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0.246|_Poor_|_Good_|_Unclassified_|Una puntuación entre 0 y 1 que se genera basándose en una combinación de experiencia de usuario, estadísticas de duración inmovilizada y experiencia de llamada general |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0.524|_Poor_|_Good_|_Unclassified_|Una puntuación entre 0 y 1 que se genera basándose en una combinación de experiencia de usuario, estadísticas de duración inmovilizada y experiencia de llamada general |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Clasificador de vídeo
Una transmisión de vídeo se marca como _Buena_ o _Mala_ en función del valor de la primera métrica disponible en el siguiente orden:

|Paso N. º|Métrica|Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50 % |_Poor_|_Good_|Continúe con el paso 2|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. El promedio incluye las tramas recuperadas de las pérdidas de red.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|>  0.15|_Poor_|_Good_|_Unclassified_|Porcentaje de pérdida de paquetes después de aplicar fec agregado en todas las transmisiones de vídeo y códecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Clasificador de VBSS

Una transmisión de VBSS se marca como _Buena_ o _Mala_ en función del valor de la primera métrica disponible en el siguiente orden:

|Paso N. º |Métrica |Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|El códec NO es H264S</br>Y</br>StreamDirection is Inbound</br></br>If FrameLoss > 50%|_Poor_|_Good_|_Unclassified_|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. El promedio incluye las tramas recuperadas de las pérdidas de red. FrameLoss solo se usa para clasificar secuencias entrantes que no son H264S.|
|2|Video Frame Rate Avg|< 1|_Poor_|_Good_|_Unclassified_|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión. Se aplica a todas las transmisiones salientes y a StreamDirection para H264S.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>Clasificador de uso compartido de aplicaciones

Una transmisión de uso compartido de aplicaciones se marca como _Mala_ si se cumplen una o varias de las condiciones siguientes:

| Métrica     | Condición | Explicación |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Porcentaje de ventanas que se descartan en lugar de enviarse a un equipo remoto (por ejemplo, del MCU a un visor). Los iconos descartados (o estropeados) pueden deberse a restricciones de ancho de banda entre el cliente y el servidor. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latencia media en milisegundos en el procesamiento de ventanas en la pila de RDP del servidor de conferencias. |
| AppSharing Relative OneWay Average | > 1,75 | Retraso medio relativo unidireccional entre los puntos de conexión en segundos durante las transmisiones con uso compartido de aplicaciones. |
| | | |

## <a name="unclassified-streams"></a>Transmisiones sin clasificar

En el CQD, una transmisión se marca como _Sin clasificar_ cuando falla la conectividad del establecimiento de conectividad interactiva (ICE) o cuando no se notifican todas las métricas necesarias para calcular la clasificación de la transmisión.

Para verificar los errores de conectividad de ICE, examine las dimensiones "ICE de primera conectividad" e "ICE de segunda conectividad" para obtener un valor "FALLO". Si alguno de los valores indica un error, la transmisión se marca como _Sin clasificar_.

Si la conectividad de ICE se realizó correctamente para una transmisión _sin clasificar_ , es probable que la transmisión se considere _sin clasificar_ porque no se registraron métricas de transmisiones clave. Hay algunas razones por las que puede que no se notifiquen estas métricas:

- **Los informes de QoE no se recibieron** : las métricas utilizadas para la clasificación se notifican en un informe de QoE enviado al final de una llamada. Si este informe no se produce (por ejemplo, porque algunos puntos de conexión de terceros pueden no enviar QoE) o no se podrían enviar (por ejemplo, debido a una interrupción de red), el CQD no puede clasificar la transmisión.

  > [!TIP]
  > La dimensión "Registro QoE disponible" se puede usar para determinar si se ha recibido un informe QoE para una transmisión. Tenga en cuenta que esta dimensión tendrá un valor de "True" si se ha recibido un informe QoE desde cualquier punto de conexión. Se requiere un informe QoE de ambos puntos de conexión para obtener el informe más preciso de las métricas.

- **Llamadas cortas** : es posible que las llamadas cortas no tengan suficiente actividad multimedia para calcular las métricas de transmisión de claves. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.

  > [!TIP]
  > Se pueden usar las dimensiones "Duración (segundos)", "Duración (minutos)", "Duración de 5 segundos o menos" y "Duración de 60 segundos o más" para determinar la duración de una transmisión. También se puede usar la medición "Duración media de la llamada" para calcular la duración media de un conjunto de transmisiones.

- **Bajo uso de paquetes** : al igual que en el escenario de "llamada corta", se requiere un uso de paquetes suficiente para calcular las métricas de flujo clave. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.
  - Un escenario común de uso bajo de paquetes se produce cuando un asistente se une a una reunión para escuchar al moderador, pero nunca habla (el micrófono está silenciado durante la mayor parte de la llamada). Aquí, la transmisión de audio entrante al cliente tiene un uso elevado de paquetes, mientras que la secuencia de audio saliente desde el cliente tiene poco o ningún uso de paquetes. La duración de la transmisión puede ser una hora o más, pero el uso de paquetes en la transmisión desde el cliente al servidor es bajo, ya que el micrófono estaba silenciado y se obtiene una secuencia _sin clasificar_ .

  > [!TIP]
  > Se pueden usar la dimensión "Utilización de paquetes" y la medición "Uso medio de paquetes" para determinar la actividad de paquetes de una transmisión.

## <a name="related-topics"></a>Temas relacionados
[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload los datos de inquilinos y compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)
