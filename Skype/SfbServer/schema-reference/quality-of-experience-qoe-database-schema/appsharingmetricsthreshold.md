---
title: Tabla AppSharingMetricsThreshold
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La tabla AppSharingMetricsThreshold contiene los valores aceptables y óptimos para las métricas de calidad de la experiencia usadas con uso compartido de aplicaciones. Estos umbrales se utilizan para determinar si la aplicación compartir experiencia debe clasificarse como deficiente.
ms.openlocfilehash: 1ccf60fc9668d2ad2943929affad6fd4a078c789
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="appsharingmetricsthreshold-table"></a>Tabla AppSharingMetricsThreshold
 
La tabla AppSharingMetricsThreshold contiene los valores aceptables y óptimos para las métricas de calidad de la experiencia usadas con uso compartido de aplicaciones. Estos umbrales se utilizan para determinar si la aplicación compartir experiencia debe clasificarse como deficiente.
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |Tipo de llamada que se colocó.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitación de ancho de banda óptimo para el uso compartido de aplicaciones. El valor predeterminado es 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitación de ancho de banda aceptable para uso compartido de aplicaciones. El valor predeterminado es 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Porcentaje óptimo para mosaicos "estropeados" para la clasificación de una calidad de uso compartido de aplicaciones. Este valor es el porcentaje del contenido de lo que comparten que no recibieron el Visor. Contenido puede descartan (o estropeado) cuando el proyecto compartidor descarta mosaicos desde el origen de los gráficos o el ASMCU descartes en mosaico mosaico desde que comparte respectivamente. El valor predeterminado es 11 por ciento.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Porcentaje aceptable de mosaicos "estropeados" para la clasificación de una calidad de uso compartido de aplicaciones. Este valor es el porcentaje del contenido de lo que comparten que no recibieron el Visor. Contenido puede descartan (o estropeado) cuando el proyecto compartidor descarta mosaicos desde el origen de los gráficos o el ASMCU descartes en mosaico mosaico desde que comparte respectivamente. El valor predeterminado es 36 por ciento.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Esta columna no se utiliza en Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Esta columna no se utiliza en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se utiliza en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se utiliza en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se utiliza en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se utiliza en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valor óptimo de retardo unidireccional relativo entre los extremos de dos medios implicados en el uso compartido de aplicaciones. Es una medición de la latencia de un solo salto. El valor predeterminado es 1,0 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valor óptimo de retardo unidireccional relativo entre los extremos de dos medios implicados en el uso compartido de aplicaciones. Es una medición de la latencia de un solo salto. El valor predeterminado es 1,75 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valor óptimo del mosaico RDP promedio de latencia en el servidor de conferencia AS de procesamiento durante la duración de la sesión de visualización. Latencia es la diferencia de tiempo entre cuando el marco de inicio está codificado en el servidor (que comparte o MCU dependiendo del escenario) y el mismo fotograma de inicio se descodifica en el Visor.  <br/> Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos. El valor predeterminado es de 200 milisegundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valor aceptable del mosaico RDP promedio de latencia en el servidor de conferencia AS de procesamiento durante la duración de la sesión de visualización. Latencia es la diferencia de tiempo entre cuando el marco de inicio está codificado en el servidor (que comparte o MCU dependiendo del escenario) y el mismo fotograma de inicio se descodifica en el Visor.  <br/> Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos. El valor predeterminado es de 200 milisegundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

