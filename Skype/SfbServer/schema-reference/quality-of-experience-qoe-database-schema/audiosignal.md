---
title: Tabla AudioSignal
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
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Cada registro representa las métricas de señal de audio de un punto de conexión. Normalmente, cada llamada tiene dos registros, uno es para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: ab918941357b85c6bcb25dcbaeb93a7be9c55f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809660"
---
# <a name="audiosignal-table"></a>Tabla AudioSignal
 
Cada registro representa las métricas de señal de audio de un punto de conexión. Normalmente, cada llamada tiene dos registros, uno es para el autor de la llamada y otro para el destinatario de la llamada. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |entero  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0: datos del destinatario de la llamada  <br/> 1: Datos del autor de la llamada  <br/> |
|**SendSignalLevel** <br/> |entero  <br/> | <br/> |Representa el nivel de señal de audio del control de ganancia post analógico. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|**RecvSignalLevel** <br/> |entero  <br/> | <br/> |Vea SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |entero  <br/> | <br/> |Representa el nivel de ruido de audio del control de ganancia post analógico. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|**RecvNoiseLevel** <br/> |entero  <br/> | <br/> |Consulte SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |entero  <br/> | <br/> |Métrica de mejora de pérdida de retorno de eco. La unidad de esta métrica es dB. Los valores inferiores representan menos eco. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |entero  <br/> | <br/> |Problemas promedio cada cinco minutos para la representación del altavoz. Para una buena calidad, debería ser inferior a uno cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no lo notifican.  <br/> |
|**AudioMicGlitchRate** <br/> |entero  <br/> | <br/> |Problemas promedio cada cinco minutos para la captura del micrófono. Para una buena calidad, debería ser inferior a uno cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no lo notifican.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Velocidad de deriva del reloj del dispositivo de micrófono, con relación al reloj de la CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Velocidad de deriva del reloj del dispositivo del altavoz, en relación con el reloj de la CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Velocidad de deriva del reloj del dispositivo del altavoz, en relación con el reloj de la CPU.  <br/> Error medio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Error de marca de tiempo de transmisión de procesamiento de altavoz promedio, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |El conmutador de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Causas de la entrada del modificador de voz:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> La causa puede ser una combinación de esas causas individuales. ENTER_VS_FORCEORCONVERGENCE solo se puede habilitar mediante la clave de registro con fines de prueba.  <br/> El tipo de datos de esta columna se cambió en Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de un evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La causa puede ser una combinación de esas causas individuales.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de tiempo en el que se detectó eco en la secuencia de captura del micrófono. Normalmente, los valores son bajos para auriculares o auriculares, y superiores para los teléfonos de altavoz o los altavoces independientes. En el caso de los dispositivos que admiten la cancelación de ecos de sonido, los valores altos indican pérdida de eco. Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Porcentaje de tiempo en el que se detecta eco en la secuencia enviada. Porcentaje de eco alto en las secuencias de envío una indicación de pérdida de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |entero  <br/> | <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace; esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser de [-30 a -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |entero  <br/> | <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser inferior a -50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |entero  <br/> | <br/> |Control de ganancia automático (AGC) en el lado del servidor de mediación.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |El cuadrado medio raíz (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |entero  <br/> ||Nivel de señal recibido en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |entero  <br/> ||Nivel de señal recibido en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |entero  <br/> ||Nivel de ruido recibido en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |entero  <br/> ||Nivel de ruido recibido en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |entero  <br/> ||Nivel de señal tal como se envía en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |entero  <br/> ||Nivel de señal tal como se envía en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |entero  <br/> ||Nivel de ruido tal como se envía en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |entero  <br/> ||Nivel de ruido tal como se envía en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |entero  <br/> ||Nivel en dBFS de la señal enviada al altavoz para su reproducción. Cuenta los ajustes de ganancia realizados en la señal recibida. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |entero  <br/> ||Nivel en dBFS del contenido de ruido en la señal enviada al altavoz para la reproducción <br/> |

