---
title: Tabla AppSharingMetricsThreshold
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
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La tabla AppSharingMetricsThreshold contiene los valores óptimos y aceptables de la métrica de la calidad de la experiencia usada con el uso compartido de aplicaciones. Estos umbrales se utilizan para determinar si la experiencia de uso compartido de aplicaciones debe calificarse como pobre.
ms.openlocfilehash: c3ee6c9742935cf7fc076c809a7aa3e09706391a58a6b1cc8025f5c5044dc5d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344599"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabla AppSharingMetricsThreshold
 
La tabla AppSharingMetricsThreshold contiene los valores óptimos y aceptables de la métrica de la calidad de la experiencia usada con el uso compartido de aplicaciones. Estos umbrales se utilizan para determinar si la experiencia de uso compartido de aplicaciones debe calificarse como pobre.
  
Esta tabla se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |Entero  <br/> |Principal  <br/> |Tipo de llamada realizada.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |Entero  <br/> ||Limitación del ancho de banda óptima para el uso compartido de aplicaciones. El valor predeterminado es 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |Entero  <br/> ||Limitación del ancho de banda aceptable para el uso compartido de aplicaciones. El valor predeterminado es 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Porcentaje óptimo para iconos "estropeados" para clasificar una calidad de uso compartido de aplicaciones. Este valor es el porcentaje del contenido del iniciador de la sesión que no llegó al visualizador. Puede que el contenido se descarte (o se deseche) cuando el iniciador de la sesión descarta mosaicos del origen de gráficos o cuando ASMCU descarta mosaicos del iniciador de la sesión, respectivamente. El valor predeterminado es 11%.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Porcentaje aceptable para iconos "estropeados" para clasificar una calidad de uso compartido de aplicaciones. Este valor es el porcentaje del contenido del iniciador de la sesión que no llegó al visualizador. Puede que el contenido se descarte (o se deseche) cuando el iniciador de la sesión descarta mosaicos del origen de gráficos o cuando ASMCU descarta mosaicos del iniciador de la sesión, respectivamente. El valor predeterminado es 36%.  <br/> |
|**JitterInterArrivalOptimal** <br/> |Entero  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |Entero  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Esta columna no se usa en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valor óptimo para el retraso unidireccional relativo entre los dos extremos multimedia implicados en el uso compartido de aplicaciones. Se trata de una medida de latencia de un solo salto. El valor predeterminado es 1,0 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valor óptimo para el retraso unidireccional relativo entre los dos extremos multimedia implicados en el uso compartido de aplicaciones. Se trata de una medida de latencia de un solo salto. El valor predeterminado es 1,75 segundos.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valor óptimo para la latencia media de procesamiento de mosaicos de RDP en el servidor de conferencia AS en la duración de la sesión de visualización. La latencia es la diferencia de tiempo entre cuando se codifica el marco de inicio en el servidor (sharer o MCU según el escenario) y el mismo marco de inicio se descodifica en el visor.  <br/> Una media elevada refleja un retraso mayor en la experiencia de visualización. Es posible que los servidores de conferencia sobrecargados experimenten, de media, retrasos mayores. El valor predeterminado es 200 ms.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valor aceptable para la latencia media de procesamiento de mosaicos de RDP en el servidor de conferencia AS en la duración de la sesión de visualización. La latencia es la diferencia de tiempo entre cuando se codifica el marco de inicio en el servidor (sharer o MCU según el escenario) y el mismo marco de inicio se descodifica en el visor.  <br/> Una media elevada refleja un retraso mayor en la experiencia de visualización. Es posible que los servidores de conferencia sobrecargados experimenten, de media, retrasos mayores. El valor predeterminado es 200 ms.  <br/> La columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

