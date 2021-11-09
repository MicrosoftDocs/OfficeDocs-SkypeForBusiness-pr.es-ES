---
title: Tabla VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para las métricas de Calidad de experiencia utilizadas con videollamadas.
ms.openlocfilehash: e0a482a0d89086463585b51e7cd6912a593ef412
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847003"
---
# <a name="videometricsthreshold-table"></a>Tabla VideoMetricsThreshold
 
La tabla VideoMetricsThreshold contiene valores óptimos y aceptables para las métricas de Calidad de experiencia utilizadas con videollamadas.
  

| **Columna**                                               | **Tipo de datos**       | **Clave/índice**  | **Detalles**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | Entero  <br/>          | Principal  <br/> | Tipo de llamada realizada.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | El valor predeterminado es 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | El valor predeterminado es 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | El valor predeterminado es 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | El valor predeterminado es 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | El valor predeterminado es 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | El valor predeterminado es 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | El valor predeterminado es 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | decimal(5,2)  <br/> |                | El valor predeterminado es 10,0.  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | El valor predeterminado es 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | El valor predeterminado es 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | El valor predeterminado es 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | El valor predeterminado es 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | El valor predeterminado es 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | El valor predeterminado es 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | El valor predeterminado es 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | El valor predeterminado es 10,00.  <br/>   |

