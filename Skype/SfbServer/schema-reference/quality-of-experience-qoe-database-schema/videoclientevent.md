---
title: Tabla VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Cada registro contiene un evento de cliente para un punto final en una videollamada. Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.'
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804998"
---
# <a name="videoclientevent-table"></a>Tabla VideoClientEvent
 
Cada registro contiene un evento de cliente para un punto final en una videollamada. Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del autor de la llamada  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentaje de sesión el evento LowBandwidth se activó por el estado "incorrecto". El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentaje de sesión el evento ReceiveSendQuality se activó por el estado "incorrecto".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta la calidad de audio que se recibe.  <br/> |
   

