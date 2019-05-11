---
title: Seleccionar reglas de conversión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Enterprise Voice requiere que todas las cadenas de marcado puede normalizar al formato E.164 con el fin de realizar la búsqueda inversa de números (RNL). El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local. Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.
ms.openlocfilehash: 9b6c1b8788742ea74508f35e402b164daf139a34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33890434"
---
# <a name="select-translation-rules"></a>Seleccionar reglas de conversión
 
 Enterprise Voice requiere que todas las cadenas de marcado puede normalizar al formato E.164 con el fin de realizar la búsqueda inversa de números (RNL). El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local. Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.
  
> [!IMPORTANT]
> La capacidad para asociar una o varias reglas de traducción con una configuración de tronco de Enterprise Voice está pensada para usarse como alternativa a la configuración de reglas de conversión en el mismo nivel de tronco. No asocie reglas de conversión con una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en el mismo nivel de tronco debido a que las dos reglas entran en conflicto. 
  
Para usar una regla de conversión existente, haga clic en una regla de la lista y, a continuación, en **Aceptar**.
  
 
  

