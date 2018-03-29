---
title: Tabla AudioSignal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Cada registro representa las métricas de señal de audio para un extremo. Normalmente, cada llamada tiene dos registros, uno es para el llamador, y uno es para el destinatario de la llamada.
ms.openlocfilehash: 25d565538ecdf7cae15ff23f539a2e2eddf8680f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="audiosignal-table"></a>Tabla AudioSignal
 
Cada registro representa las métricas de señal de audio para un extremo. Normalmente, cada llamada tiene dos registros, uno es para el llamador, y uno es para el destinatario de la llamada. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del llamador  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Representa el nivel de señal de audio analógica posteriores al Control de ganancia. La unidad para que esta métrica es dBmo. Para obtener una calidad aceptable, debe ser al menos 30 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Consulte SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Representa el nivel de ruido de audio analógico posteriores al Control de ganancia. La unidad para que esta métrica es dBmo. Para una calidad aceptable, debería ser inferior a 35 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Consulte SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Métrica de mejora de la pérdida de eco devolver. La unidad para que esta métrica es dB. Los valores más bajos representan menos eco. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Problemas técnicos promedio por cinco minutos para la representación de altavoz. Para la buena calidad debe ser menor que una por cinco minutos. No informa A / teléfonos IP, servidores de mediación o servidores de conferencia V.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Problemas técnicos promedio por cinco minutos para la captura de micrófono. Para la buena calidad debe ser menor que una por cinco minutos. No informa A / teléfonos IP, servidores de mediación o servidores de conferencia V.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Micrófono dispositivo deriva velocidad de reloj, con respecto al reloj de la CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Altavoz dispositivo deriva velocidad de reloj, con respecto al reloj de la CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Altavoz dispositivo deriva velocidad de reloj, con respecto al reloj de la CPU.  <br/> Promedio de micrófono captura secuencia marca error de tiempo, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Altavoz medio representar error de sello de tiempo de secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Modificador de voz es un modo semidúplex con posibilidad de reducción de las interrupciones. Causas de la entrada del interruptor de voz:  <br/> ENTER_VS_BADTS 0 X 01  <br/> ENTER_VS_ECHO 0 X 02  <br/> ENTER_VS_FORCEORCONVERGENCE 0 X 04  <br/> ENTER_VS_DNLP 0 X 08  <br/> La causa puede ser una combinación de esas causas individuales. ENTER_VS_FORCEORCONVERGENCE sólo puede habilitarse mediante la clave de registro para el propósito de la prueba.  <br/> El tipo de datos de esta columna se cambió en Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de un evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0 X 01  <br/> ECHO_EVENT_POSTAEC_ECHO 0 X 02  <br/> ECHO_EVENT_ANLP 0 X 04  <br/> ECHO_EVENT_DNLP 0 X 08  <br/> ECHO_EVENT_MIC_CLIPPING 0 X 10  <br/> ECHO_EVENT_BAD_STATE 0 X 20  <br/> La causa puede ser una combinación de esas causas individuales.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Porcentaje de tiempo cuando se detecta el eco en secuencia enviado. Porcentaje de eco alta en enviar secuencias de una indicación de pérdida de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Nivel de señal en el servidor de mediación procedente de la puerta de enlace; Esto se aplica sólo para el servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el rango aceptable debe ser [-30 a -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Nivel de señal recibida en el servidor de mediación de la puerta de enlace. Esto se aplica sólo para el servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el rango aceptable debe ser inferior a-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Control (AGC) en el servidor de mediación de ganancia automático.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |La raíz cuadrada Media (RMS) de la señal de entrada de hasta los primeros 30 segundos de la llamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Nivel de la señal medida reciben en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Nivel de señal como recibido en canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Nivel de ruido como recibido en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Nivel de ruido como recibido en canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Nivel de señal como enviadas en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Nivel de señal como enviadas en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Nivel de ruido como enviadas en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Nivel de ruido como enviadas en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
   

