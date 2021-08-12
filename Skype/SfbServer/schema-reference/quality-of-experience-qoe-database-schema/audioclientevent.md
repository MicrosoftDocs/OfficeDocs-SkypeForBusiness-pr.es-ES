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
description: Cada registro contiene un evento de cliente para un punto de conexión en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para la persona que llama y otro para el destinatario de la llamada.
ms.openlocfilehash: f92c77178630bfb6f04e8c707565993fd24c16873a3dc74461eee0ba11884599
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309219"
---
# <a name="audioclientevent-table"></a>Tabla AudioClientEvent
 
Cada registro contiene un evento de cliente para un punto de conexión en una llamada de audio. Normalmente, una llamada tiene dos registros, uno para la persona que llama y otro para el destinatario de la llamada.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0: Datos del destinatario de la llamada  <br/> 1: Datos del autor de la llamada  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento NetworkSendQuality en estado "Bad".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento ReceiveSendQuality en estado "Bad".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se recibe.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento Delay en estado "Bad". La latencia de red es grave y afecta a la experiencia al impedir la comunicación interactiva  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento LowBandwidth en estado "Bad". El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en el que se despidió el evento cpu insuficiente para el estado "Malo". No hay ciclos de CPU suficientes para procesar con las modalidades y aplicaciones actuales en uso. Esto provoca distorsión con el canal de audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceHalfDuplexAEC en estado "Bad". Para evitar el eco, el sistema ha ingresado medio dúplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceRenderNotFunctioning en estado "Bad". El dispositivo de representación que se está utilizando actualmente para la sesión no funciona correctamente. Esto puede provocar problemas de audio uni-way.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceCaptureNotFunctioning en estado "Bad". El dispositivo de captura que se está utilizando actualmente para la sesión no funciona correctamente. Esto puede provocar problemas de audio uni-way.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceGlitches en estado "Bad". Hay problemas graves en la representación de audio que están causando distorsión. Estos problemas pueden deberse a problemas de controladores, llamadas de procedimiento diferido (DPC) de tormenta (controladores) y un alto uso de CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceLowSNR en estado "Bad". La calidad de captura es muy mala, ya sea muy ruidosa o el usuario está hablando demasiado lejos del micrófono. Esto provocará distorsión.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceLowSpeechLevel en estado "Bad". El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo más. Esto puede provocar distorsión o se percibe como audio universado.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceClipping en estado "Bad".  <br/> Cuando la voz casi al final recorta el micrófono, el extremo lejano escucha la distorsión debido al recorte. Es importante evitar el recorte de micrófono casi al final.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceEchoEvent en estado "Bad". El dispositivo o la configuración está provocando eco más allá de la capacidad del sistema para compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de sesión en la que se despidió el evento DeviceNearEndToEchoRatio para el estado "Bad". La voz del usuario es demasiado baja en comparación con el eco que se captura, lo que afecta a la experiencia de los usuarios porque limita lo fácil que es interrumpir a un usuario. Reducir el volumen del altavoz, acercar el micrófono al hablador.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |Entero  <br/> ||Número de veces durante la sesión el evento DeviceMultipleEndpoints se ha desencadenado para el estado "Bad". Varios puntos de conexión de audio en la misma sesión detectados y el sistema ha compensado al reducir el volumen de representación.  <br/> |
|**DeviceHowlingEventCount** <br/> |Entero  <br/> | <br/> |Número de veces durante la sesión el evento DeviceHowlingEvent se despidió en estado "Bad". Bucle de comentarios de audio detectado (causado por varios puntos de conexión que comparten la ruta de audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión en la que se despidió el evento DeviceRenderZeroVolume por estar en el estado "Malo". El dispositivo de representación se estableció en volumen cero.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Porcentaje de sesión en la que se despidió el evento DeviceRenderMute por estar en el estado "Bad". El dispositivo de representación se ha silenciado.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

