---
title: Tabla VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene un evento de cliente para un punto de conexión en una videollamada. Normalmente, una llamada tiene dos registros, uno para la persona que llama y otro para el destinatario de la llamada.
ms.openlocfilehash: 8c2f9142bb187fec8ceb55c34ea28c7f62b06d23
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858937"
---
# <a name="videoclientevent-table"></a>Tabla VideoClientEvent
 
Cada registro contiene un evento de cliente para un punto de conexión en una videollamada. Normalmente, una llamada tiene dos registros, uno para la persona que llama y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0: Datos del destinatario de la llamada  <br/> 1: Datos del autor de la llamada  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentaje de sesión en la que se despidió el evento LowBandwidth en estado "Bad". El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentaje de sesión en la que se despidió el evento ReceiveSendQuality en estado "Bad".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.  <br/> |
   

