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
description: La tabla SessionCorrelation es una tabla compatible. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802660"
---
# <a name="sessioncorrelation-table"></a>Tabla SessionCorrelation
 
La tabla SessionCorrelation es una tabla compatible. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Suma de comprobación** <br/> |entero  <br/> |||
|**CorrelationKey** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica este servidor de conferencia A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Única  <br/> |Las sesiones correlacionadas tendrán el mismo identificador de correlación.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Únicamente para uso interno.  <br/> |
   

