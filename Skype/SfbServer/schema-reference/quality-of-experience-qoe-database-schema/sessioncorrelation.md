---
title: Tabla SessionCorrelation
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: En la tabla SessionCorrelation es una tabla de apoyo. Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212119"
---
# <a name="sessioncorrelation-table"></a>Tabla SessionCorrelation
 
En la tabla SessionCorrelation es una tabla de apoyo. Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Suma de comprobación** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este / servidor de conferencia A/v.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Único  <br/> |Las sesiones correlacionadas tendrán el mismo identificador de correlación.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Sólo para uso interno.  <br/> |
   

