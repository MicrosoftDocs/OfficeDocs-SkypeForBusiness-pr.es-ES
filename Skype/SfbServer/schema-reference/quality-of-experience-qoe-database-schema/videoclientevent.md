---
title: Tabla VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contiene el evento de cliente para un extremo en una videollamada. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821400"
---
# <a name="videoclientevent-table"></a>Tabla VideoClientEvent
 
Cada registro contiene el evento de cliente para un extremo en una videollamada. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |entero  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0: datos del destinatario de la llamada  <br/> 1: Datos del autor de la llamada  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Porcentaje de sesión en la que se deseó el evento LowBandwidth para el estado "Bad". El ancho de banda disponible no es suficiente para una experiencia de voz aceptable.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Porcentaje de sesión en la que se deseó el evento ReceiveSendQuality para el estado "Bad".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.  <br/> |
   

