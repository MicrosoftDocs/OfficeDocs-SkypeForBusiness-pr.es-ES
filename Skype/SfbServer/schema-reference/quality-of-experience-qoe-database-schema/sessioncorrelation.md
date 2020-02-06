---
title: Tabla SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es una tabla de soporte. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805748"
---
# <a name="sessioncorrelation-table"></a>Tabla SessionCorrelation
 
La tabla SessionCorrelation es una tabla de soporte. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Comprobación** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este servidor de conferencia A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Solo  <br/> |Las sesiones correlacionadas tendrán el mismo identificador de correlación.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Solo para uso interno.  <br/> |
   

