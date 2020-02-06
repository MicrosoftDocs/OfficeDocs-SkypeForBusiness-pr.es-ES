---
title: Tabla AudioClientEvent
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 'Cada registro contiene un evento de cliente para un punto final en una llamada de audio. Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.'
ms.openlocfilehash: 713804875f9cd2a1fc37a2255697c4ffda47a3c5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811088"
---
# <a name="audioclientevent-table"></a>Tabla AudioClientEvent
 
Cada registro contiene un evento de cliente para un punto final en una llamada de audio. Generalmente, una llamada tiene dos registros: uno para el autor de la llamada y otro para el destinatario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del autor de la llamada  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento NetworkSendQuality se activó por el estado "incorrecto".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta a la calidad del audio que se envía.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento ReceiveSendQuality se activó por el estado "incorrecto".  <br/> La calidad de la red en términos de vibración o pérdida de paquetes es grave y afecta la calidad de audio que se recibe.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de la sesión el evento de retraso se activó para el estado "incorrecto". La latencia de la red es grave y afecta a la experiencia al evitar la comunicación interactiva  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento LowBandwidth se activó por el estado "incorrecto". El ancho de banda disponible es insuficiente para una experiencia de voz aceptable.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento de CPU insuficiente se activó para el estado "incorrecto". No hay suficientes ciclos de CPU para procesar con las aplicaciones y las aplicaciones actuales en uso. Esto causa distorsiones en el canal de audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceHalfDuplexAEC se activó por el estado "incorrecto". Para evitar que se produzca el eco, el sistema se introduce a doble cara.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceRenderNotFunctioning se activó por el estado "incorrecto". El dispositivo de representación que se usa actualmente para la sesión no funciona correctamente. Esto puede dar lugar a problemas de audio unidireccionales.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceCaptureNotFunctioning se activó por el estado "incorrecto". El dispositivo de captura usado actualmente para la sesión no funciona correctamente. Esto puede dar lugar a problemas de audio unidireccionales.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceGlitches se activó por el estado "incorrecto". Hay problemas graves en la representación de audio que causan distorsiones. Estos problemas pueden estar causados por problemas de controlador, tormentas de llamadas a procedimiento diferidas (DPC) y uso intensivo de la CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceLowSNR se activó por el estado "incorrecto". La calidad de la captura es muy mala, ya sea muy ruidosa o el usuario habla demasiado lejos del micrófono. Esto provocará distorsiones.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceLowSpeechLevel se activó por el estado "incorrecto". El nivel de voz del usuario es demasiado bajo y el sistema no puede aumentarlo. Esto puede causar distorsiones o percibir como audio unidireccional.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceClipping se activó por el estado "incorrecto".  <br/> Cuando los recortes de voz próximos se recortan, el micrófono escucha la distorsión del extremo a causa de la recorte. Es importante evitar el recorte de micrófono cerca de la final.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceEchoEvent se activó por el estado "incorrecto". El dispositivo o el programa de instalación está causando eco más allá de la capacidad del sistema para compensar.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de sesión el evento DeviceNearEndToEchoRatio se activó por el estado "incorrecto". La voz del usuario es demasiado baja en comparación con el eco que se está capturando y que afecta a la experiencia de los usuarios porque limita lo fácil que es interrumpir a un usuario. Reduce el volumen del altavoz, mueve el micrófono cerca de la Talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Número de veces durante la sesión el evento DeviceMultipleEndpoints se activó por el estado "incorrecto". Se detectaron varios puntos de conexión de audio en la misma sesión y el sistema se ha compensado al reducir el volumen de representación.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Número de veces durante la sesión el evento DeviceHowlingEvent se activó por el estado "incorrecto". Se detectó un bucle de comentarios de audio (causado por varios puntos de conexión que comparten la ruta de audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal (4,5)  <br/> ||Porcentaje de sesión el evento DeviceRenderZeroVolume se activó por estar en el estado "incorrecto". El dispositivo de representación se estableció en un volumen de cero.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal (4,5)  <br/> ||Porcentaje de sesión el evento DeviceRenderMute se activó por estar en el estado "incorrecto". El dispositivo de representación se ha silenciado.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

