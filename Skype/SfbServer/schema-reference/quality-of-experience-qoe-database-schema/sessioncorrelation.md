---
title: Tabla SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es una tabla de soporte técnico. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 2029d78a0a083bcf8817b3a819cd28e74824995d79575036ecafd85998bd5218
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314426"
---
# <a name="sessioncorrelation-table"></a>Tabla SessionCorrelation
 
La tabla SessionCorrelation es una tabla de soporte técnico. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Suma de comprobación** <br/> |Entero  <br/> |||
|**CorrelationKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este servidor de conferencia A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Única  <br/> |Las sesiones correlacionadas tendrán el mismo identificador de correlación.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Únicamente para uso interno.  <br/> |
   

