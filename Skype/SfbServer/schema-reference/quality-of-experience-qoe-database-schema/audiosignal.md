---
title: Tabla AudioSignal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Cada registro representa las métricas de señal de audio de un extremo. Normalmente, cada llamada tiene dos registros, uno es para el autor de la llamada, y uno es para el destinatario de la llamada.
ms.openlocfilehash: 7a064f13b6f34f61dcfb72169a4b1620cd81b01f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895121"
---
# <a name="audiosignal-table"></a>Tabla AudioSignal
 
Cada registro representa las métricas de señal de audio de un extremo. Normalmente, cada llamada tiene dos registros, uno es para el autor de la llamada, y uno es para el destinatario de la llamada. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del autor de la llamada  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Representa el nivel de Control de ganancia analógica posteriores a la señal de audio. La unidad de esta métrica es dBmo. Para una calidad aceptable, debería ser al menos 30 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Consulte SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Representa el nivel de ruido de audio de Control de ganancia posterior a la analógica. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Consulte SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Métrica de mejora de pérdida de eco devolver. La unidad para que esta métrica es la base de datos. Los valores más bajos representan menos eco. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Problemas técnicos promedio por cinco minutos para la representación de altavoz. De buena calidad, debe ser menor que uno por cada cinco minutos. No informa A / teléfonos IP, los servidores de mediación o servidores de conferencia A/v.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Problemas técnicos promedio por cinco minutos para la captura del micrófono. De buena calidad debe ser menor que uno por cada cinco minutos. No informa A / teléfonos IP, los servidores de mediación o servidores de conferencia A/v.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Micrófono dispositivo desfase del reloj del, con respecto al reloj de la CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Altavoz dispositivo desfase del reloj del, con respecto al reloj de la CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Altavoz dispositivo desfase del reloj del, con respecto al reloj de la CPU.  <br/> Promedio de micrófono captura errores tiempo de secuencia marca, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Presentación del altavoz promedio errores de marca de tiempo de secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Modificador de voz es un modo de dúplex con capacidad de reducción de las interrupciones. Causas de entrada de conmutador de voz:  <br/> ENTER_VS_BADTS 0 X 01  <br/> ENTER_VS_ECHO 0 X 02  <br/> ENTER_VS_FORCEORCONVERGENCE 0 X 04  <br/> ENTER_VS_DNLP 0 X 08  <br/> La causa puede ser una combinación de causas individuales. ENTER_VS_FORCEORCONVERGENCE sólo se puede habilitar mediante la clave del registro para el propósito de la prueba.  <br/> El tipo de datos para esta columna se cambió en Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de un evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0 X 01  <br/> ECHO_EVENT_POSTAEC_ECHO 0 X 02  <br/> ECHO_EVENT_ANLP 0 X 04  <br/> ECHO_EVENT_DNLP 0 X 08  <br/> ECHO_EVENT_MIC_CLIPPING 0 X 10  <br/> ECHO_EVENT_BAD_STATE 0 X 20  <br/> La causa puede ser una combinación de causas individuales.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Porcentaje de tiempo cuando se detecta el eco en secuencia enviado. Porcentaje de eco alta en enviar secuencias de una indicación de pérdida de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Recibido el nivel de señal en el servidor de mediación de la puerta de enlace; Esto se aplica sólo al servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el intervalo aceptable debe ser [-30 a -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Nivel de señal recibida en el servidor de mediación desde la puerta de enlace. Esto se aplica sólo al servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el intervalo aceptable debe ser menor que-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Control (AGC) en el lado del servidor de mediación de ganancia automático.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |El valor cuadrático (RMS) de la señal entrante de los primeros 30 segundos de la llamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Nivel de señal según se recibe en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Nivel de señal según se recibe en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Nivel de ruido según se recibe en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Nivel de ruido según se recibe en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Nivel de señal según se envía en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Nivel de señal según se envía en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Nivel de ruido según se envía en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Nivel de ruido según se envía en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Nivel en dBFS de la señal se envía para el altavoz para la reproducción. Cuentas para los ajustes de ganancia realizadas a la señal recibida. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Nivel de dBFS del contenido de ruido de la señal se envía para el altavoz de reproducción <br/> |

