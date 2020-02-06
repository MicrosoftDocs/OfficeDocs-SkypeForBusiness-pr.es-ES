---
title: Tabla VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para la medición de la calidad de la medición que se usa con las videollamadas.
ms.openlocfilehash: 89d3095ef7222cacc7633116c43d66cbcc2be2e2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804740"
---
# <a name="videometricsthreshold-table"></a>Tabla VideoMetricsThreshold
 
La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para la medición de la calidad de la medición que se usa con las videollamadas.
  

| **Columna**                                               | **Tipo de datos**       | **Clave o índice**  | **Detalles**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | Tipo de llamada que se realizó.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal (4,5)  <br/> |                | El valor predeterminado es 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal (4,5)  <br/> |                | El valor predeterminado es 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal (4,5)  <br/> |                | El valor predeterminado es 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal (4,5)  <br/> |                | El valor predeterminado es 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal (9, 4)  <br/> |                | El valor predeterminado es 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal (9, 4)  <br/> |                | El valor predeterminado es 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal (4,5)  <br/> |                | El valor predeterminado es 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimal (4,5)  <br/> |                | El valor predeterminado es 10,0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal (4,5)  <br/> |                | El valor predeterminado es 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal (4,5)  <br/> |                | El valor predeterminado es 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | El valor predeterminado es 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | El valor predeterminado es 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | El valor predeterminado es 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | El valor predeterminado es 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal (4,5)  <br/> |                | El valor predeterminado es 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal (4,5)  <br/> |                | El valor predeterminado es 10,00.  <br/>   |

