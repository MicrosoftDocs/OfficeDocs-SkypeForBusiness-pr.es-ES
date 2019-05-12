---
title: Tabla VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene eventos de cliente para uno de los extremos en una llamada de vídeo. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906829"
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
   

