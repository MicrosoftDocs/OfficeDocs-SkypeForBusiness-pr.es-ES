---
title: Clasificación de la transmisión en el panel de calidad de llamadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Descubra cómo se clasifica la calidad de la transmisión en el panel de calidad de llamadas para Microsoft Teams y Skype for Business Online.
ms.openlocfilehash: a77ca0605589c99b88ba3287bf8febcc7514cbd1
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23783561"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Clasificación de la transmisión en el panel de calidad de llamadas

El panel de calidad de llamadas (CQD) para Microsoft Teams y Skype para profesionales en línea permite obtener entendimiento de la calidad de las llamadas realizadas mediante Microsoft Teams y Skype para servicios de negocios. Este tema proporciona información detallada sobre la clasificación de calidad de las transmisiones multimedia. Para obtener más información sobre CQD y cómo habilitarlo, vea [activar y con el panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definiciones del clasificador

Las transmisiones en el panel de calidad de llamadas se clasifican como buenas, malas o sin clasificar en función de los valores de las métricas clave de calidad disponibles. En las tablas siguientes se muestran las métricas y condiciones utilizadas para clasificar la transmisión. Se pueden usar las dimensiones "Mala debido a" del panel de calidad de llamadas para comprender qué métrica es responsable de una clasificación deficiente. Para obtener más información sobre estas dimensiones, consulte [Dimensiones y medidas disponibles en el panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Clasificador de audio

Una transmisión de audio se marca como mala si se cumplen una o más de las condiciones siguientes:

|**Métrica**|**Condición**|**Explicación**|
|:-----|:-----|:-----|
|Audio Degradation Avg|>1,0|Media de degradación de la puntuación de opinión media de la red en la transmisión. Representa qué cantidad de vibración y pérdida de red ha influido en la calidad del audio recibido.|
|Round Trip|>500|Tiempo medio de ida y vuelta en la propagación de red que se calcula como se especifica en RFC3550 en milisegundos.|
|Packet Loss Rate|>0,1|Porcentaje medio de pérdida de paquetes en la transmisión.|
|Jitter|>30|Vibración media producida en la transmisión en milisegundos.|
|Ratio Concealed Samples Avg|> 0,07|Relación media del número de marcos de audioconferencias con muestras ocultas generadas por la pérdida de resolución de problemas y el número total de marcos de audioconferencias.|

### <a name="video-classifier"></a>Clasificador de vídeo

Una transmisión de vídeo se marca como buena o mala según el valor de la primera métrica disponible, en el orden siguiente:

|**Paso n. º**|**Métrica**|**Condición**|**Clasificación si la condición es verdadera**|**Clasificación si la condición es falsa**|**Clasificación si la métrica no está disponible**|**Explicación**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Continúe con el paso 2|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. Se incluyen los fotogramas que se recuperan de las pérdidas de red.|
|2|Video Frame Rate Avg|< 7|Poor|Good|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Tasa de pérdida de paquetes después de que se ha aplicado FEC agregados a través de todas las secuencias de vídeo y códecs.|

### <a name="vbss-classifier"></a>Clasificador de VBSS

Una transmisión de VBSS se marca como buena o mala según el valor de la primera métrica disponible, en el orden siguiente:

|**Paso N. º**|**Métrica**|**Condición**|**Clasificación si la condición es verdadera**|**Clasificación si la condición es falsa**|**Clasificación si la métrica no está disponible**|**Explicación**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |Poor|Good|Continúe con el paso 2|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. Se incluyen los fotogramas que se recuperan de las pérdidas de red.|
|2|Video Frame Rate Avg|<2|Poor|Good|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|>  0.15|Poor|Good|Unclassified|Tasa de pérdida de paquetes después de que se ha aplicado FEC agregados a través de todas las secuencias de vídeo y códecs.|

### <a name="application-sharing-classifier"></a>Clasificador de uso compartido de aplicaciones

Una transmisión de uso compartido de aplicaciones se marca como mala si se cumplen una o más de las condiciones siguientes:

**Métrica**|**Condición**|**Explicación**|
|:-----|:-----|:-----|
|Spoiled Tile Percent Total|> 36|Porcentaje de mosaicos que se descartan en lugar de enviarse a un interlocutor remoto (por ejemplo, de la MCU a un visor). Mosaicos descartados (o estropeados) pueden deberse a restricciones de ancho de banda entre cliente y servidor.|
|AppSharing RDP Tile Processing Latency Average|400 >|Latencia media en milisegundos en el procesamiento de ventanas en la pila de RDP del servidor de conferencias.|
|AppSharing Relative OneWay Average|> 1,75|Retraso medio de relativa unidireccional entre los extremos en segundos para el uso compartido de secuencias de aplicaciones.|

## <a name="unclassified-streams"></a>Transmisiones sin clasificar

En el panel de calidad de llamadas, una transmisión se marca como sin clasificar cuando falla la conectividad de ICE o cuando no se notifican todas las métricas necesarias para calcular la clasificación de la transmisión.

Para verificar los errores de conectividad de ICE, examine las dimensiones "ICE de primera conectividad" e "ICE de segunda conectividad" para obtener un valor "FALLO". Si cualquiera de los dos valores indica un error, la transmisión se marcará como sin clasificar.

Si la conectividad ICE es correcta para una transmisión sin clasificar, la transmisión probablemente se considere sin clasificar porque no se han notificado las métricas clave de transmisión. Hay algunas razones por las que puede que no se notifiquen estas métricas:

- **No se han recibido informes QoE**: las métricas utilizadas para la clasificación se notifican en un informe QoE enviado al final de una llamada. Si no se genera este informe (por ejemplo, porque puede que algunos puntos de conexión de terceros no envíen QoE) o no se ha podido enviar (por ejemplo, debido a una interrupción de la red), el panel de calidad de llamadas no puede clasificar la transmisión.

> [!TIP]
> La dimensión "Registro QoE disponible" se puede usar para determinar si se ha recibido un informe QoE para una transmisión. Tenga en cuenta que esta dimensión tendrá un valor de "True" si se ha recibido un informe QoE desde cualquier punto de conexión. Se requiere un informe QoE de ambos puntos de conexión para obtener el informe más preciso de las métricas.

- **Llamadas cortas**: es posible que las llamadas cortas no tengan suficiente actividad de elementos multimedia para calcular las métricas clave de transmisión. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.

> [!TIP]
> Se pueden usar las dimensiones "Duración (segundos)", "Duración (minutos)", "Duración de 5 segundos o menos" y "Duración de 60 segundos o más" para determinar la duración de una transmisión. También se puede usar la medición "Duración media de la llamada" para calcular la duración media de un conjunto de transmisiones.

- **Baja utilización de paquetes**: al igual que el escenario de "llamada corta", se requiere una utilización de paquetes suficiente para el cálculo de las métricas clave de transmisión. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.
    - Un escenario común de baja utilización de paquetes se produce cuando un usuario se une a una reunión para escuchar al presentador pero nunca habla (probablemente silenciando el micrófono durante la mayor parte de la conferencia). En este escenario, una transmisión de audio tendrá una alta utilización de paquetes (entrantes al cliente) mientras que la otra tendrá poca o ninguna utilización de paquetes (salientes desde el cliente). En este escenario, la duración de la transmisión puede ser de una hora o más, pero la utilización de paquetes en la transmisión del cliente al servidor será extremadamente baja debido a que el micrófono está silenciado, lo que da como resultado una transmisión sin clasificar.

> [!TIP]
> Se pueden usar la dimensión "Utilización de paquetes" y la medición "Uso medio de paquetes" para determinar la actividad de paquetes de una transmisión.


## <a name="related-topics"></a>Temas relacionados
[Activar y usar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar Análisis de llamadas para solucionar problemas de mala calidad de llamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)
