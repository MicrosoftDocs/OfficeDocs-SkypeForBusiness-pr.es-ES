---
title: Tabla AudioSignal
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
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Cada registro representa las métricas de señal de audio de un extremo. Normalmente, cada llamada tiene dos registros, uno para la persona que llama y el otro es para el destinatario de la llamada.
ms.openlocfilehash: d1b35aa4111feb77ae905e833d7bb1f4d4acd01e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810678"
---
# <a name="audiosignal-table"></a>Tabla AudioSignal
 
Cada registro representa las métricas de señal de audio de un extremo. Normalmente, cada llamada tiene dos registros, uno para la persona que llama y el otro es para el destinatario de la llamada. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: datos del destinatario de la llamada  <br/> 1: datos del autor de la llamada  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Representa el nivel de señal de audio de control de ganancia posterior analógico. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Consulta SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Representa el nivel de ruido de audio del control de ganancia posterior analógico. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Consulta SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Métrica de mejora de pérdida de eco. La unidad para esta métrica es dB. Los valores más bajos representan menos eco. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Promedio de problemas por cinco minutos para el procesamiento de altavoz. Para obtener una buena calidad, debe ser inferior a un período de 5 minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Promedio de problemas por cinco minutos para la captura del micrófono. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal (9; 2)  <br/> | <br/> |Velocidad de desplazamiento del reloj del dispositivo de micrófono, relativa al reloj de la CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal (9; 2)  <br/> | <br/> |Velocidad de desplazamiento del reloj del dispositivo de altavoz, relativa al reloj de la CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal (9; 2)  <br/> | <br/> |Velocidad de desplazamiento del reloj del dispositivo de altavoz, relativa al reloj de la CPU.  <br/> Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal (9; 2)  <br/> | <br/> |El altavoz promedio representa el error de marca de tiempo de la secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Causas de la entrada de conmutación de voz:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> La causa puede ser una combinación de estas causas individuales. RegKey solo puede habilitar ENTER_VS_FORCEORCONVERGENCE para fines de prueba.  <br/> El tipo de datos de esta columna se modificó en Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de un evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La causa puede ser una combinación de estas causas individuales.  <br/> |
|**EchoPercentMicIn** <br/> |decimal (4,5)  <br/> | <br/> |Porcentaje de tiempo para la detección del eco en la secuencia de captura del micrófono. En general, los valores son bajos para auriculares, y altos para altavoces de teléfono o independientes. En el caso de dispositivos que son compatibles con la cancelación del eco acústico incorporada, los valores altos indican filtraciones de eco. En otros dispositivos, esta métrica no debe utilizarse para evaluar la calidad del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal (4,5)  <br/> ||Porcentaje de tiempo durante el que se detecta eco en el flujo enviado. Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser [-30 a-18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Control automático de ganancia (AGC) en el servidor de mediación.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |El cuadrado de la media raíz (RMS) de la señal entrante de hasta los primeros 30 segundos de la llamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Nivel de señal como recibido en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Nivel de señal como recibido en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Nivel de ruido recibido en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Nivel de ruido recibido en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Nivel de señal enviado en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Nivel de señal enviado en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Nivel de ruido enviado en el canal 1.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Nivel de ruido enviado en el canal 2.  <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Nivel en dBFS de la señal enviada al altavoz para la reproducción. Cuenta los ajustes de ganancia realizados en la señal recibida. <br/> Esta columna se introdujo en Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Nivel en dBFS del contenido de ruido en la señal enviada al altavoz para su reproducción <br/> |

