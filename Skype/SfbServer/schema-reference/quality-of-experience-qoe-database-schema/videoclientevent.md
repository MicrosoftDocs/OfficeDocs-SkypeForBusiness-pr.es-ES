---
title: Tabla VideoClientEvent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene el evento de cliente para un extremo en una videollamada. Normalmente, una llamada tiene dos registros, uno para el llamador y otro para el destinatario de la llamada.
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a>Tabla VideoClientEvent
 
Cada registro contiene el evento de cliente para un extremo en una videollamada. Normalmente, una llamada tiene dos registros, uno para el llamador y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del llamador  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentaje de sesión que se desencadenó el evento LowBandwidth para el estado 'Bad'. El ancho de banda disponible no es suficiente para una experiencia de voz aceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentaje de sesión que se desencadenó el evento ReceiveSendQuality para el estado 'Bad'.  <br/> Calidad de la red en términos de pérdida de paquete o Vibración es grave y afecta a la calidad del audio que se recibe.  <br/> |
   

