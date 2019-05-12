---
title: Tabla SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: En la tabla SessionCorrelation es una tabla de apoyo. Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 4efd1aeba45fb12aee646c401f492450f375aa20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907083"
---
# <a name="sessioncorrelation-table"></a>Tabla SessionCorrelation
 
En la tabla SessionCorrelation es una tabla de apoyo. Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Suma de comprobación** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este / servidor de conferencia A/v.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Único  <br/> |Las sesiones correlacionadas tendrán el mismo identificador de correlación.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Sólo para uso interno.  <br/> |
   

