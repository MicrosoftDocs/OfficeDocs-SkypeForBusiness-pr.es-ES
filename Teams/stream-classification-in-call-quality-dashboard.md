---
title: Clasificación de la transmisión en el panel de calidad de llamadas (CQD)
ms.author: lolajacobsen
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
description: Obtenga información sobre cómo se clasifica la calidad de la transmisión en el panel de calidad de llamadas (CQD) para Microsoft Teams y Skype empresarial online.
ms.openlocfilehash: 28c3857f1bf30903e9a59d45e8149f8ecbfc57be
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085896"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Clasificación de la transmisión en el panel de calidad de llamadas (CQD)

El panel de calidad de llamadas (CQD) para Microsoft Teams y Skype empresarial online le permite obtener información sobre la calidad de las llamadas hechas con Microsoft Teams y los servicios de Skype empresarial. En este tema, se proporciona información detallada sobre la clasificación de calidad de las transmisiones multimedia. Para obtener más información sobre el CQD y cómo configurarlo, consulte [configurar el panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definiciones del clasificador

Las transmisiones en el CQD se clasifican como _buenas_, _malas_o no _clasificadas_ en función de los valores de las métricas de calidad de clave disponibles. Las métricas y condiciones que se usan para clasificar la secuencia se muestran en las tablas siguientes. Las dimensiones de "mala calidad de los CQDs" pueden usarse para comprender qué métrica es responsable de una clasificación _deficiente_ . Para obtener más información sobre estas dimensiones, consulte [dimensiones y medidas disponibles en el panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Clasificador de audio

Si se cumplen una o varias de las siguientes condiciones, una secuencia de audio se marca como _mala_:

|Métrica|Condición|Explicación|
|:-----|:-----|:-----|
|Audio Degradation Avg|>1,0|Promedio de media de puntuación de la red: degradación de la transmisión. La cantidad de pérdida de la red y de vibración han influyedo en la calidad del audio recibido.|
|Round Trip|>500|Promedio de tiempo de propagación de red de ida y vuelta, que se calcula en milisegundos. Detalles disponibles en [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Packet Loss Rate|>0,1|Porcentaje medio de pérdida de paquetes en la transmisión.|
|Vibración|>30|Vibración media producida en la transmisión en milisegundos.|
|Ratio Concealed Samples Avg|> 0,07|Relación media entre el número de marcos de audio con muestras ocultas generada por la recuperación de pérdida de paquetes para el número total de marcos de audio.|
||||

### <a name="video-classifier-due-to-freeze"></a>Clasificador de vídeos por inmovilizar

La secuencia de vídeo se marca como _buena_ o _mala_ según el valor de una puntuación de clasificador generada para estimar que el usuario final experimentó un vídeo congelado. Este clasificador solo está disponible para los productos de Microsoft Teams.

|Paso N. º|Métrica|Escenario|Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Vídeo de mala calidad debido al clasificador de inmovilizado |¿Es el par de servidores el cliente: servidor?|>0,246|_Poor_|_Good_|_Unclassified_|Una puntuación entre 0 y 1 que se genera en función de una combinación de experiencia del usuario, inmovilizar estadísticas de duración y realizar llamadas generales. |
|2|Vídeo de mala calidad debido al clasificador de inmovilizado |Is el par de servidores es cliente: cliente|>0,524|_Poor_|_Good_|_Unclassified_|Una puntuación entre 0 y 1 que se genera en función de una combinación de experiencia del usuario, inmovilizar estadísticas de duración y realizar llamadas generales. |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Clasificador de vídeo
Una secuencia de vídeo se marca como _buena_ o _mala_ según el valor de la primera métrica disponible en el siguiente orden:

|Paso N. º|Métrica|Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Continúe con el paso 2|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. El promedio incluye las imágenes recuperadas de pérdidas de red.|
|2|Video Frame Rate Avg|< 7|_Poor_|_Good_|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|>  0.15|_Poor_|_Good_|_Unclassified_|La tasa de pérdida de paquetes después de que se haya aplicado FEC en todas las transmisiones y códecs de vídeo.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Clasificador de VBSS

Una secuencia VBSS se marca como _buena_ o _mala_ según el valor de la primera métrica disponible en el siguiente orden:

|Paso N. º |Métrica |Condición |Clasificación si la condición es verdadera |Clasificación si la condición es falsa |Clasificación si la métrica no está disponible |Explicación |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Poor_|_Good_|Continúe con el paso 2|Porcentaje medio de fotogramas de vídeo perdidos cuando se muestran al usuario. El promedio incluye las imágenes recuperadas de pérdidas de red.|
|2|Video Frame Rate Avg|<2|_Poor_|_Good_|Continúe con el paso 3|Media de fotogramas por segundo que se reciben en una transmisión de vídeo, calculada a lo largo de la sesión.|
|3|Video Post FECPLR|>  0.15|_Poor_|_Good_|_Unclassified_|La tasa de pérdida de paquetes después de que se haya aplicado FEC en todas las transmisiones y códecs de vídeo.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Clasificador de uso compartido de aplicaciones

Una secuencia de uso compartido de aplicaciones se marca como _mala_ si se cumplen una o varias de las siguientes condiciones:

| Métrica     | Condición | Explicación |
|:---        |:---       | :--- |
| Spoiled Tile Percent Total | > 36 | Porcentaje de mosaicos que se descartan en lugar de enviarse a un interlocutor remoto (por ejemplo, de la MCU a un visor). Los mosaicos descartados pueden estar causados por restricciones de ancho de banda entre el cliente y el servidor. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latencia media en milisegundos en el procesamiento de ventanas en la pila de RDP del servidor de conferencias. |
| AppSharing Relative OneWay Average | > 1,75 | Promedio de retraso relativo promedio entre los puntos de conexión en segundos para las transmisiones de uso compartido de aplicaciones. |
| | | |

## <a name="unclassified-streams"></a>Transmisiones sin clasificar

En el CQD, una secuencia se marca como no _clasificada_ cuando se produce un error en la conectividad de establecimiento interactivo de conectividad (ICE) o cuando no se notifican todas las métricas necesarias para calcular la clasificación de transmisión por secuencias.

Para verificar los errores de conectividad de ICE, examine las dimensiones "ICE de primera conectividad" e "ICE de segunda conectividad" para obtener un valor "FALLO". Si alguno de los valores indica un error, la secuencia se marca como no _clasificada_.

Si la conectividad de ICE se realizó correctamente para una transmisión sin _clasificar_ , es probable que la secuencia se considere no _clasificada_ porque no se informaron las métricas de secuencia de claves. Hay algunas razones por las que puede que no se notifiquen estas métricas:

- **No se recibieron informes de QoE** : las métricas usadas para la clasificación se notifican en un informe de QoE enviado al final de una llamada. Si este informe no se genera (por ejemplo, porque algunos puntos de conexión de terceros pueden no enviar el QoE) o no se pudo enviar (por ejemplo, a causa de un corte en la red), el CQD no puede clasificar la transmisión.

> [!TIP]
> La dimensión "Registro QoE disponible" se puede usar para determinar si se ha recibido un informe QoE para una transmisión. Tenga en cuenta que esta dimensión tendrá un valor de "True" si se ha recibido un informe QoE desde cualquier punto de conexión. Se requiere un informe QoE de ambos puntos de conexión para obtener el informe más preciso de las métricas.

- **Llamadas cortas** : es posible que las llamadas cortas no tengan suficiente actividad multimedia para calcular las métricas de las secuencias de teclas. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.

> [!TIP]
> Se pueden usar las dimensiones "Duración (segundos)", "Duración (minutos)", "Duración de 5 segundos o menos" y "Duración de 60 segundos o más" para determinar la duración de una transmisión. También se puede usar la medición "Duración media de la llamada" para calcular la duración media de un conjunto de transmisiones.

- **Baja utilización de paquetes** : al igual que el escenario de "llamada breve", se requiere una utilización suficiente de los paquetes para calcular las métricas de las secuencias de teclas. Sin estas métricas, el panel de calidad de llamadas no puede clasificar la transmisión.
  - Un escenario muy bajo de uso de paquetes se produce cuando un asistente se une a una reunión para escuchar al moderador, pero nunca habla (el micrófono está silenciado para la mayor parte de la llamada). Aquí, la transmisión de audio entrante al cliente tiene un uso elevado de paquetes, mientras que la transmisión de audio saliente del cliente tiene poco o ningún paquete de uso. La duración de la transmisión puede ser de una hora o más larga, pero el uso de paquetes en la transmisión desde el cliente al servidor es bajo, ya que el micrófono se ha silenciado y se ha producido un flujo sin _clasificar_ .

> [!TIP]
> Se pueden usar la dimensión "Utilización de paquetes" y la medición "Uso medio de paquetes" para determinar la actividad de paquetes de una transmisión.

## <a name="related-topics"></a>Temas relacionados
[Mejorar y supervisar la calidad de las llamadas de los equipos](monitor-call-quality-qos.md)

[¿Qué es el CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar inquilino y datos de compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md)
