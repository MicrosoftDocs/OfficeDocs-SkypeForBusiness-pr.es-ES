---
title: Tabla VideoClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene eventos de cliente para uno de los extremos en una llamada de vídeo. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891244"
---
# <a name="videoclientevent-table"></a>Tabla VideoClientEvent
 
Cada registro contiene eventos de cliente para uno de los extremos en una llamada de vídeo. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del autor de la llamada  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentaje de sesión que se desencadenó el evento LowBandwidth para estado 'Bad'. El ancho de banda disponible no es suficiente para obtener una experiencia de voz aceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentaje de sesión que se desencadenó el evento ReceiveSendQuality para estado 'Bad'.  <br/> Calidad de red en cuanto a vibración o pérdida de paquetes es baja y afecta a la calidad del audio que se recibe.  <br/> |
   

