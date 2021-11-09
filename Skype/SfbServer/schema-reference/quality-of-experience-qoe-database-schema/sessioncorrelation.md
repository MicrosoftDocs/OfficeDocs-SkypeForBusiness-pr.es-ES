---
title: Tabla SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es una tabla de soporte técnico. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 706bd5c47d1a709712c7178562e535612f61332c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834908"
---
# <a name="sessioncorrelation-table"></a>Tabla SessionCorrelation
 
La tabla SessionCorrelation es una tabla de soporte técnico. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Suma de comprobación** <br/> |Entero  <br/> |||
|**CorrelationKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este servidor de conferencia A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Única  <br/> |Las sesiones correlacionadas tendrán el mismo identificador de correlación.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Únicamente para uso interno.  <br/> |
   

