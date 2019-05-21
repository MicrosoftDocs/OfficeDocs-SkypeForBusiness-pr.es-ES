---
title: Tabla AppSharingMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La tabla AppSharingMetricsThreshold contiene valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con el uso compartido de aplicaciones. Estos umbrales se usan para determinar si la experiencia de uso compartido de aplicaciones se debe clasificar como mala.
ms.openlocfilehash: d3e7bab384c5fffea59e165d5fdf4e6b3d0c09a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295128"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabla AppSharingMetricsThreshold
 
La tabla AppSharingMetricsThreshold contiene valores óptimos y aceptables para las métricas de la calidad de la experiencia que se usan con el uso compartido de aplicaciones. Estos umbrales se usan para determinar si la experiencia de uso compartido de aplicaciones se debe clasificar como mala.
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |Tipo de llamada que se realizó.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Límite de ancho de banda óptimo para compartir aplicaciones. El valor predeterminado es 1 millón.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitación de ancho de banda aceptable para el uso compartido de aplicaciones. El valor predeterminado es 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal (4,5)  <br/> ||Tasa de porcentaje óptima para los mosaicos "estropeados" para clasificar la calidad de uso compartido de una aplicación. Este valor es el porcentaje del contenido del que el que comparte no ha podido comunicarse con el visor. El contenido puede ser descartado (o estropeado) cuando el compartidor descarta los mosaicos del origen de los gráficos o los mosaicos de ASMCU descarta los mosaicos del compartidor, respectivamente. El valor predeterminado es 11 por ciento.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal (4,5)  <br/> ||Tasa de porcentaje aceptable para los mosaicos "estropeados" para clasificar la calidad de uso compartido de una aplicación. Este valor es el porcentaje del contenido del que el que comparte no ha podido comunicarse con el visor. El contenido puede ser descartado (o estropeado) cuando el compartidor descarta los mosaicos del origen de los gráficos o los mosaicos de ASMCU descarta los mosaicos del compartidor, respectivamente. El valor predeterminado es 36 por ciento.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valor óptimo para el retraso relativo relativo entre los dos extremos multimedia implicados en el uso compartido de la aplicación. Es una medición de la latencia de un solo salto. El valor predeterminado es 1,0 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valor óptimo para el retraso relativo relativo entre los dos extremos multimedia implicados en el uso compartido de la aplicación. Es una medición de la latencia de un solo salto. El valor predeterminado es 1,75 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valor óptimo de la latencia media de procesamiento de mosaicos RDP en el servidor de conferencia como durante la duración de la sesión de visualización. Latencia es la diferencia horaria entre cuando el fotograma inicial está codificado en el servidor (compartidor o MCU, según el escenario) y se descodifica el mismo fotograma de inicio en el visor.  <br/> Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos. El valor predeterminado es 200ms.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valor aceptable de la latencia media de procesamiento de mosaicos RDP en el servidor de conferencia como durante la duración de la sesión de visualización. Latencia es la diferencia horaria entre cuando el fotograma inicial está codificado en el servidor (compartidor o MCU, según el escenario) y se descodifica el mismo fotograma de inicio en el visor.  <br/> Una media alta refleja un retraso mayor en la experiencia de visualización. Un servidor de conferencias sobrecargado podría experimentar una media mayor de retrasos. El valor predeterminado es 200ms.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

