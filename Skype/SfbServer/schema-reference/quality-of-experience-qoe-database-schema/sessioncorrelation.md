---
title: Tabla SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es un auxiliar. Cada registro representa un CorrelationID que se utiliza para relacionar varias sesiones.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a>Tabla SessionCorrelation
 
La tabla SessionCorrelation es un auxiliar. Cada registro representa un CorrelationID que se utiliza para relacionar varias sesiones. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Suma de comprobación** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este A / V Conferencing Server.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Único  <br/> |Las sesiones que se correlacionan tendrán el mismo identificador de correlación.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Sólo para uso interno.  <br/> |
   

