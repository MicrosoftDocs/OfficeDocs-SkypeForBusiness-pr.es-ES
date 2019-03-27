---
title: Tabla AppSharingMetricsThreshold
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: En la tabla AppSharingMetricsThreshold contiene los valores aceptables y óptimos para la métrica de calidad de la experiencia que se usa con el uso compartido de aplicaciones. Usa estos umbrales para determinar si la aplicación de uso compartido de experiencia debe clasificarse como deficiente.
ms.openlocfilehash: bddad99803ab6683985b0f44ed5df509b84344f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877045"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabla AppSharingMetricsThreshold
 
En la tabla AppSharingMetricsThreshold contiene los valores aceptables y óptimos para la métrica de calidad de la experiencia que se usa con el uso compartido de aplicaciones. Usa estos umbrales para determinar si la aplicación de uso compartido de experiencia debe clasificarse como deficiente.
  
En esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |Tipo de llamada que se realizó.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitación de ancho de banda óptimo para uso compartido de aplicaciones. El valor predeterminado es 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitación de ancho de banda aceptable para uso compartido de aplicaciones. El valor predeterminado es 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Tasa de porcentaje óptima para mosaicos "estropeados" para la clasificación de una calidad de uso compartido de aplicaciones. Este valor es el porcentaje del contenido de la persona que comparte que no llega al Visor. Contenido puede descartado (o dañado) cuando la persona que comparte descarta mosaicos desde el origen de gráficos o el ASMCU se organizan en mosaico descarta se organizan en mosaico de la persona que comparte respectivamente. El valor predeterminado es 11 por ciento.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Tasa de porcentaje aceptable para mosaicos "estropeados" para la clasificación de una calidad de uso compartido de aplicaciones. Este valor es el porcentaje del contenido de la persona que comparte que no llega al Visor. Contenido puede descartado (o dañado) cuando la persona que comparte descarta mosaicos desde el origen de gráficos o el ASMCU se organizan en mosaico descarta se organizan en mosaico de la persona que comparte respectivamente. El valor predeterminado es 36 por ciento.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valor óptimo para el retraso relativo unidireccional entre los extremos de dos medios implicados en el uso compartido de aplicaciones. Es una medición de la latencia de un solo salto. El valor predeterminado es 1,0 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valor óptimo para el retraso relativo unidireccional entre los extremos de dos medios implicados en el uso compartido de aplicaciones. Es una medición de la latencia de un solo salto. El valor predeterminado es 1,75 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valor óptimo del mosaico RDP promedio de latencia en el servidor de conferencia AS de procesamiento a través de la duración de la sesión de visualización. Latencia es la diferencia de tiempo entre cuando el marco de inicio está codificado en el servidor (que comparte o MCU en función del escenario) y el mismo fotograma de inicio se descodifica en el Visor.  <br/> Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos. El valor predeterminado es de 200 milisegundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valor aceptable del mosaico RDP promedio de latencia en el servidor de conferencia AS de procesamiento a través de la duración de la sesión de visualización. Latencia es la diferencia de tiempo entre cuando el marco de inicio está codificado en el servidor (que comparte o MCU en función del escenario) y el mismo fotograma de inicio se descodifica en el Visor.  <br/> Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos. El valor predeterminado es de 200 milisegundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

