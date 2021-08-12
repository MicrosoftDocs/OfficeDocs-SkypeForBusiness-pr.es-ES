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
description: Cada registro representa métricas de señal de audio para un punto de conexión. Normalmente, cada llamada tiene dos registros, uno es para el autor de la llamada y otro para el destinatario de la llamada.
ms.openlocfilehash: 36ece4a9481400c3fae9e248d00cc59f3ec161b21aa03d8e824fc4d21931d04f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309209"
---
# <a name="audiosignal-table"></a>Tabla AudioSignal
 
Cada registro representa métricas de señal de audio para un punto de conexión. Normalmente, cada llamada tiene dos registros, uno es para el autor de la llamada y otro para el destinatario de la llamada. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0: Datos del destinatario de la llamada  <br/> 1: Datos del autor de la llamada  <br/> |
|**SendSignalLevel** <br/> |Entero  <br/> | <br/> |Representa el nivel de señal de audio del control de ganancia posterior a analógico. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|**RecvSignalLevel** <br/> |Entero  <br/> | <br/> |Vea SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |Entero  <br/> | <br/> |Representa el nivel de ruido de audio del control de ganancia posterior a analógico. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|**RecvNoiseLevel** <br/> |Entero  <br/> | <br/> |Consulte SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |Entero  <br/> | <br/> |Métrica de mejora de pérdida de retorno de eco. La unidad de esta métrica es dB. Los valores inferiores representan menos eco. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |Entero  <br/> | <br/> |Error promedio por cinco minutos para la representación del altavoz. Para una buena calidad, debería ser inferior a uno por cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no notifican.  <br/> |
|**AudioMicGlitchRate** <br/> |Entero  <br/> | <br/> |Errores promedio por cinco minutos para la captura del micrófono. Para una buena calidad, esto debe ser inferior a uno por cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no notifican.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Velocidad de deriva del reloj del dispositivo de micrófono, en relación con el reloj de CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Velocidad de deriva del reloj del dispositivo del altavoz, con relación al reloj de CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Velocidad de deriva del reloj del dispositivo del altavoz, con relación al reloj de CPU.  <br/> Error promedio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |El altavoz promedio representa el error de marca de tiempo de secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |El conmutador de voz es un modo semidúplex con capacidad de interrupción reducida. Causas de la entrada del conmutador de voz:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> La causa puede ser una combinación de esas causas individuales. ENTER_VS_FORCEORCONVERGENCE solo se puede habilitar mediante regkey para fines de prueba.  <br/> El tipo de datos de esta columna se cambió en Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de un evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La causa puede ser una combinación de esas causas individuales.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Porcentaje de tiempo en el que se detectó eco en la secuencia de captura de micrófono. Por lo general, los valores son bajos para auriculares o auriculares, y superiores para teléfonos de altavoces o altavoces independientes. En el caso de los dispositivos que admiten la cancelación de eco acústico abordo, los valores altos indican una pérdida de eco. Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Porcentaje de tiempo en el que se detecta eco en la secuencia enviada. Alto porcentaje de eco en secuencias de envío una indicación de pérdida de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |Entero  <br/> | <br/> |Nivel de señal recibido en el servidor de mediación desde la puerta de enlace; esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser [-30 a -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |Entero  <br/> | <br/> |Nivel de señal recibido en el servidor de mediación desde la puerta de enlace. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser inferior a -50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |Entero  <br/> | <br/> |Control automático de ganancia (AGC) en el lado del servidor de mediación.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |El cuadrado medio raíz (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |Entero  <br/> ||Nivel de señal tal como se recibe en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |Entero  <br/> ||Nivel de señal tal como se recibe en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |Entero  <br/> ||Nivel de ruido recibido en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |Entero  <br/> ||Nivel de ruido recibido en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |Entero  <br/> ||Nivel de señal tal como se envía en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |Entero  <br/> ||Nivel de señal tal como se envía en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |Entero  <br/> ||Nivel de ruido tal como se envía en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |Entero  <br/> ||Nivel de ruido tal como se envía en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |Entero  <br/> ||Nivel en dBFS de la señal enviada al altavoz para la reproducción. Cuenta los ajustes de ganancia realizados en la señal recibida. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |Entero  <br/> ||Nivel en dBFS del contenido de ruido en la señal enviada al altavoz para la reproducción <br/> |

