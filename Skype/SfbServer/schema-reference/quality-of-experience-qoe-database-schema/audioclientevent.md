---
title: Tabla AudioClientEvent
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Cada registro contiene un evento de cliente para un extremo en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: f5211d7f4ec3bc1d366d97def06edd325c448def
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809690"
---
# <a name="audioclientevent-table"></a>Tabla AudioClientEvent
 
Cada registro contiene un evento de cliente para un extremo en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |entero  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0: datos del destinatario de la llamada  <br/> 1: Datos del autor de la llamada  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento NetworkSendQuality para el estado "Bad".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento ReceiveSendQuality para el estado "Bad".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento Delay para el estado "Bad". La latencia de red es grave y afecta a la experiencia al impedir la comunicación interactiva  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento LowBandwidth para el estado "Bad". El ancho de banda disponible no es suficiente para una experiencia de voz aceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento de CPU insuficiente para el estado "Mal". No hay suficientes ciclos de CPU para el procesamiento con las modalidades y aplicaciones actuales en uso. Esto provoca distorsión con el canal de audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceHalfDuplexAEC para el estado "Bad". Para evitar el eco, el sistema ha entrar en el dúplex medio.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceRenderNotFunctioning para el estado "Bad". El dispositivo de representación que se usa actualmente para la sesión no funciona correctamente. Esto puede causar problemas de audio un solo sentido.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceCaptureNotFunctioning para el estado "Bad". El dispositivo de captura que se usa actualmente para la sesión no funciona correctamente. Esto puede causar problemas de audio un solo sentido.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceGlitches para el estado "Bad". Hay problemas graves en la representación de audio que causan distorsión. Estos problemas pueden deberse a problemas de controladores, llamadas a procedimiento diferidos (controladores) y un uso elevado de CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceLowSNR para el estado "Bad". La calidad de captura es muy mala, ya sea muy ruidoso o el usuario está hablando demasiado lejos del micrófono. Esto provocará distorsión.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceLowSpeechLevel para el estado "Bad". El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo más. Esto puede causar distorsión o se percibe como audio un solo sentido.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceClipping para el estado "Bad".  <br/> Cuando la voz de extremo cercano recorta el micrófono, el extremo oirá la distorsión debido al recorte. Es importante evitar el recorte de micrófonos de extremo cercano.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceEchoEvent para el estado "Bad". El dispositivo o la configuración está provocando eco más allá de la capacidad del sistema para compensarlo.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se deseó el evento DeviceNearEndToEchoRatio para el estado "Bad". La voz del usuario es demasiado baja en comparación con el eco que se captura, lo que afecta a la experiencia de los usuarios porque limita lo fácil que es interrumpir a un usuario. Reduzca el volumen del altavoz, mueva el micrófono más cerca del hablante.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |entero  <br/> ||Número de veces durante la sesión que el evento DeviceMultipleEndpoints se ha desencadenado para el estado "Bad". Se detectaron varios puntos de conexión de audio en la misma sesión y el sistema ha compensado al reducir el volumen de representación.  <br/> |
|**DeviceHowlingEventCount** <br/> |entero  <br/> | <br/> |Número de veces durante la sesión que el evento DeviceHowlingEvent se ha desencadenado para el estado "Bad". Se detectó un bucle de comentarios de audio (causado por varios puntos de conexión que comparten la ruta de acceso de audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión en la que se deseó el evento DeviceRenderZeroVolume por estar en estado "Mal". El dispositivo de representación se estableció en cero volumen.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión en la que se deseó el evento DeviceRenderMute por estar en estado "Mal". Se ha silenciado el dispositivo de representación.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

