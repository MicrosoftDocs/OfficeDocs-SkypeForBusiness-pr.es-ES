---
title: Tabla AudioClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Cada registro contiene un evento de cliente para uno de los extremos en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: 307406446d71adf462cdc8a0345aa823129a8f99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212323"
---
# <a name="audioclientevent-table"></a>Tabla AudioClientEvent
 
Cada registro contiene un evento de cliente para uno de los extremos en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para el autor de la llamada y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del autor de la llamada  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento NetworkSendQuality para estado 'Bad'.  <br/> Calidad de red en cuanto a vibración o pérdida de paquetes es baja y afecta la calidad del audio que se envía.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento ReceiveSendQuality para estado 'Bad'.  <br/> Calidad de red en cuanto a vibración o pérdida de paquetes es baja y afecta la calidad del audio que se recibe.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento de retraso para estado 'Bad'. Latencia de red es baja y afecta a la experiencia de evitando comunicación interactiva  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento LowBandwidth para estado 'Bad'. El ancho de banda disponible no es suficiente para obtener una experiencia de voz aceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento de CPU insuficiente para estado 'Bad'. No hay suficientes ciclos de CPU para el procesamiento con el actuales modalidades y las aplicaciones en uso. Esto hace que las distorsiones con el canal de audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceHalfDuplexAEC para estado 'Bad'. Para evitar el eco, el sistema ha escriba dúplex medio.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceRenderNotFunctioning para estado 'Bad'. El dispositivo de presentación se utiliza actualmente para la sesión no está funcionando correctamente. Esto puede provocar problemas de audio unidireccionales.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceCaptureNotFunctioning para estado 'Bad'. El dispositivo de captura se utiliza actualmente para la sesión no está funcionando correctamente. Esto puede provocar problemas de audio unidireccionales.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceGlitches para estado 'Bad'. Hay problemas técnicos graves en la representación de audio que es que se produzcan distorsiones. Estos problemas técnicos pueden deberse a problemas de controlador, tormenta de llamadas (DPC) de procedimiento diferido (controladores) y el uso de CPU alta.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceLowSNR para estado 'Bad'. La calidad de captura es muy poca calidad, ya sea muy ruido o usuario está hablando demasiado lejos del micrófono. Esto hará que las distorsiones.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceLowSpeechLevel para estado 'Bad'. El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo cualquier aún más. Esto puede hacer que las distorsiones o percibe como audio unidireccional.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceClipping para estado 'Bad'.  <br/> Cuando cerca de end voz clips del micrófono, otro extremo escucha distorsión debido a recorte. Es importante evitar el recorte de micrófono cerca final.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceEchoEvent para estado 'Bad'. El programa de instalación o de dispositivo es la causa del eco más allá de la capacidad del sistema para compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión que se desencadenó el evento DeviceNearEndToEchoRatio para estado 'Bad'. Voz del usuario es demasiado baja en comparación con el eco que se capturan que afecta a la experiencia de los usuarios ya que limita lo fácil que es interrumpir un usuario. Reducir el volumen del altavoz, mueva más cerca del micrófono para el orador.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Número de veces durante la sesión que se desencadenó el evento DeviceMultipleEndpoints para el estado de 'Bad'. Varios extremos de audio en la misma sesión que detecta y el sistema ha compensación al reducir el volumen de procesamiento.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Número de veces durante la sesión que se desencadenó el evento DeviceHowlingEvent para el estado de 'Bad'. Ha detectado un bucle la retroalimentación de audio (causados por varios extremos, uso compartido de ruta de audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión que se desencadenó el evento DeviceRenderZeroVolume para que se está en la "incorrecta ' estado. El dispositivo de presentación se estableció en cero volumen.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión que se desencadenó el evento DeviceRenderMute para que se está en la "incorrecta ' estado. Se ha desactivado el dispositivo de presentación.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

