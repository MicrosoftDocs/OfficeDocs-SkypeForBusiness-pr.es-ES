---
title: Tabla AudioClientEvent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Cada registro contiene un evento de cliente para un extremo en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para el llamador y otro para el destinatario de la llamada.
ms.openlocfilehash: dd910c9abf5cbd8d95a7448f72b49641148a2c64
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="audioclientevent-table"></a>Tabla AudioClientEvent
 
Cada registro contiene un evento de cliente para un extremo en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para el llamador y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del llamador  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento NetworkSendQuality para el estado 'Bad'.  <br/> Calidad de la red en términos de pérdida de paquete o Vibración es grave y afectar a la calidad de audio que se envían.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento ReceiveSendQuality para el estado 'Bad'.  <br/> Calidad de la red en términos de pérdida de paquete o Vibración es grave y afectar a la calidad de audio que se recibe.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento de demora de estado 'Bad'. Latencia de la red es grave y afectar a la experiencia impidiendo la comunicación interactiva  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento LowBandwidth para el estado 'Bad'. El ancho de banda disponible no es suficiente para una experiencia de voz aceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento CPU suficiente para estado 'Bad'. No hay suficientes ciclos de CPU para el proceso con el actuales modalidades y aplicaciones en uso. Esto hace que las distorsiones con el canal de audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceHalfDuplexAEC para el estado 'Bad'. Para evitar el eco, el sistema ha ENTRAR dúplex medio.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceRenderNotFunctioning para el estado 'Bad'. El dispositivo de representación se utiliza actualmente para la sesión no está funcionando correctamente. Esto puede causar problemas de audio unidireccionales.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceCaptureNotFunctioning para el estado 'Bad'. El dispositivo de captura que se utiliza actualmente para la sesión no está funcionando correctamente. Esto puede causar problemas de audio unidireccionales.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceGlitches para el estado 'Bad'. Hay problemas técnicos graves en el procesamiento de audio que es que se produzcan distorsiones. Estos problemas pueden deberse a problemas de controladores, tormenta de llamadas (DPC) de procedimiento diferido (controladores) y uso intensivo de la CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceLowSNR para el estado 'Bad'. La calidad de captura es muy deficiente, puede ser muy ruidoso o usuario está hablando demasiado lejos del micrófono. Esto hará que las distorsiones.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceLowSpeechLevel para el estado 'Bad'. Nivel de voz del usuario es demasiado bajo y el sistema no aumentarlo cualquier aún más. Esto puede hacer que las distorsiones o percibe como audio unidireccional.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceClipping para el estado 'Bad'.  <br/> Cuando los clips de voz cerca del final del micrófono, extremo oye distorsión debido al recorte. Es importante evitar el recorte de micrófono cerca del final.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceEchoEvent para el estado 'Bad'. Dispositivo o instalación produce eco más allá de la capacidad del sistema para compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceNearEndToEchoRatio para el estado 'Bad'. Voz del usuario es demasiado bajo en comparación con el eco va a capturar lo que afecta a la experiencia de los usuarios ya que limita lo fácil que es interrumpir un usuario. Reducir el volumen del altavoz, mueva hacia el micrófono para el orador.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Número de veces durante la sesión que se desencadenó el evento DeviceMultipleEndpoints para el estado 'Bad'. Varios extremos de audio en la misma sesión detectado y el sistema ha compensado reduciendo el volumen de procesamiento.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Número de veces durante la sesión que se desencadenó el evento DeviceHowlingEvent para el estado 'Bad'. Ha detectado un bucle de realimentación de audio (causada por varios extremos compartiendo ruta de audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión que se desencadenó el evento DeviceRenderZeroVolume para estar en la "Bad' estado. El dispositivo de representación se estableció en volumen cero.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión que se desencadenó el evento DeviceRenderMute para estar en la "Bad' estado. Se ha silenciado el dispositivo de representación.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

