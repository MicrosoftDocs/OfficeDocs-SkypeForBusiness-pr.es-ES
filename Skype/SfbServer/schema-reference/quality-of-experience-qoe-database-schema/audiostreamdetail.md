---
title: Vista AudioStreamDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: La vista AudioStreamDetail almacena información acerca de cada secuencia de audio en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c5078a0d936cce0dec29ddfee3813db7334aba71
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895289"
---
# <a name="audiostreamdetail-view"></a>Vista AudioStreamDetail
 
La vista AudioStreamDetail almacena información acerca de cada secuencia de audio en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Identificador único dentro de una línea de medios.  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de inicio de la sesión.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría del diálogo: 0 es la Skype para Business Server tramo de servidor de mediación; 1 es el servidor de mediación para tramo de puerta de enlace de RTC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Marca que indica si la llamada se pasó o no.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Si está presente, indica ¿por qué una llamada no se pasó incluso si el desvío de los identificadores de coinciden. Se define un solo valor:  <br/> 0 x 0001 - identificador de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridad de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de autor de la llamada.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatario de la llamada.  <br/> |
|Autor de llamada  <br/> |nvarchar(450)  <br/> |Del autor de la URI.  <br/> |
|Destinatario de la llamada  <br/> |nvarchar(450)  <br/> |Del destinatario de la URI.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del autor de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del autor de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener información detallada. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría de agente de usuario del autor de la llamada. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener información detallada. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario de destinatario de la llamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo del destinatario de la llamada agente de usuario. Consulte la [tabla UserAgent](useragent.md) para obtener información. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría de agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener información. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del autor de la llamada.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del destinatario de la llamada.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Sistema operativo (SO) del extremo del autor de la llamada.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Sistema operativo (SO) del extremo del destinatario de la llamada.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Nombre de la CPU del extremo del autor de la llamada.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Nombre de la CPU del extremo del destinatario de la llamada.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU en el extremo del llamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU en el extremo del destinatario de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del extremo del autor de la llamada.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del extremo del destinatario de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema el autor de la llamada se está ejecutando en un entorno virtualizado. Vea la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado. Vea la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|CorrelationKey  <br/> ||Clave de correlación. Referencia de la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Obtener información acerca de la ruta de acceso de medios, como directa o retransmitido. Consulte la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) describe en bits indicadores para el autor de la llamada. Para obtener información detallada, consulte la calidad de experiencia Monitoring Server especificación del protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) describe en bits indicadores para el destinatario de la llamada. Para obtener información detallada, consulte la calidad de experiencia Monitoring Server especificación del protocolo.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte: 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP del autor de la llamada. Esto puede resultar una IPv4 o una dirección IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto usado por el autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la red del intervalo: 1 significa autor de la llamada está dentro de la red de empresa, 0 significa que el autor de la llamada está fuera de la red.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Esto puede resultar una IPv4 o una dirección IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto usado por el destinatario de la llamada.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el destinatario de la llamada está dentro de la red del intervalo: 1 significa destinatario de la llamada está dentro de la red de empresa, 0 significa que el destinatario está fuera de la red.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del autor de la llamada.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del autor de la llamada.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del destinatario de la llamada.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del destinatario de la llamada.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/v utilizado por el autor de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Puerto usado en el servicio perimetral A/v utilizado por el autor de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Tecla de dirección IP del servicio perimetral A/v que usa el destinatario de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto usado en el servicio perimetral A/v que usa el destinatario de la llamada.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nombre del dispositivo de presentación de autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de presentación del autor de la llamada.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nombre del dispositivo de presentación del destinatario de la llamada.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de presentación del destinatario de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del autor de la llamada: 0 es cableada, 1 es inalámbrica.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad del vínculo de red de extremo del autor de la llamada en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del destinatario de la llamada: 0 es cableada, 1 es inalámbrica.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el autor de la llamada se conectó a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad del vínculo de red de extremo del destinatario de la llamada en bps.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Ancho de banda real aplicada a la secuencia de lado de envío determinado dada distintas configuraciones de directivas (activar, API, SDP, servidor de directivas y así sucesivamente). Esto no es debe confundirse con el ancho de banda eficaz debido a que puede haber un ancho de banda eficaz inferior en función de la estimación del ancho de banda. Esto es, básicamente, el ancho de banda máximo que se puede realizar la secuencia de envío a excepción de los límites de impuestas por la estimación del ancho de banda  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Vibración de red promedio de las estadísticas del protocolo de Control de tiempo Real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Frecuencia de pérdida de paquetes promedio durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Máximo la pérdida de paquetes observada durante la llamada.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Densidad media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|BurstDuration  <br/> |int  <br/> |Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Densidad media de pérdida de paquetes durante intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Duración media de intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Número de paquetes de la secuencia de audio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Previsiones de ancho de banda de la secuencia de audio.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red para la llamada completa. Rango es 0,0 a 5.0. Esta métrica muestra la cantidad que se ha reducido la MOS de red debido a la pérdida de paquetes y vibración. Para que una calidad aceptable debe menor que 0,5.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red máxima durante la llamada.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red provocada por la vibración.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red provocada por la pérdida.  <br/> |
|PayloadDescription  <br/> |int  <br/> |El códec de audio utilizado para la llamada, de la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Velocidad de muestreo de la secuencia de audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Nivel de señal de audio de Control de ganancia posteriores a la analógica para el audio que envía el autor de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debería ser al menos 30 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Nivel de señal de audio para el audio del autor de llamada recibido. La unidad de esta métrica es dBmo. Para una calidad aceptable, debería ser al menos 30 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Nivel de ruido de audio de Control de ganancia posteriores a la analógico para el audio que envía el autor de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Nivel de ruido de audio de Control de ganancia posteriores a la analógico para el audio recibido a través del autor de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Eco devolver mejora pérdida para el autor de la llamada. La unidad para que esta métrica es la base de datos. Los valores más bajos representan menos eco. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Problemas técnicos promedio por cinco minutos para la representación de altavoz del autor de la llamada. De buena calidad, debe ser menor que uno por cada cinco minutos. No informa A / teléfonos IP, los servidores de mediación o servidores de conferencia A/v.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Capturan problemas técnicos promedio por cinco minutos para micrófono del autor de la llamada. De buena calidad debe ser menor que uno por cada cinco minutos. No informa A / teléfonos IP, los servidores de mediación o servidores de conferencia A/v.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Micrófono dispositivo desfase del reloj del autor de la llamada, con respecto al reloj de la CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Altavoz dispositivo desfase del reloj del autor de la llamada, con respecto al reloj de la CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Promedio de micrófono captura errores tiempo de secuencia marca, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Promedio de altavoz del autor de la llamada de representación errores de marca de tiempo de secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Modificador de voz es un modo de dúplex con capacidad de reducción de las interrupciones. Consulte la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causas de un evento de eco para el autor de la llamada. Consulte la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en secuencia de captura del micrófono del autor de la llamada. Si se usan auriculares con micrófono, el valor debe ser bajo.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en el autor de la llamada del envía la secuencia. Porcentaje de eco alta en enviar secuencias de una indicación de pérdida de eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Nivel de señal recibida en el servidor de mediación desde la puerta de enlace para el audio del autor de la llamada; Esto se aplica sólo al servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el intervalo aceptable debe ser -30 a dBoV-18.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Audio de nivel de señal recibida en el servidor de mediación desde la puerta de enlace para el autor de la llamada. Esto se aplica sólo al servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el intervalo aceptable debe ser menor que-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Automático control de ganancia (AGC) en el lado del servidor de mediación aplicado al audio del autor de la llamada.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Valor cuadrático medio (RMS) de la señal entrante que el autor de la llamada para los primeros 30 segundos de la llamada.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Representa el nivel de Control de ganancia analógica posteriores a la señal de audio para el audio enviado el destinatario de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debería ser al menos 30 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Nivel de señal de audio para el audio del destinatario de llamada recibido. La unidad de esta métrica es dBmo. Para una calidad aceptable, debería ser al menos 30 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Nivel de ruido de audio de Control de ganancia posteriores a la analógico para el audio que envía el destinatario de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Nivel de ruido de audio de Control de ganancia posteriores a la analógico para el audio recibido a través del destinatario de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Eco devolver mejora pérdida para el destinatario de la llamada. La unidad para que esta métrica es la base de datos. Los valores más bajos representan menos eco. Esta métrica no se notifica el / los teléfonos IP o servidor de conferencia A/v.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Problemas técnicos promedio por cinco minutos para la representación de altavoz del destinatario de la llamada. De buena calidad, debe ser menor que uno por cada cinco minutos. No informa A / teléfonos IP, los servidores de mediación o servidores de conferencia A/v.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Capturan problemas técnicos promedio por cinco minutos para micrófono del destinatario de la llamada. De buena calidad debe ser menor que uno por cada cinco minutos. No informa A / teléfonos IP, los servidores de mediación o servidores de conferencia A/v.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Micrófono dispositivo desfase del reloj del destinatario de la llamada, con respecto al reloj de la CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Altavoz dispositivo desfase del reloj del destinatario de la llamada, con respecto al reloj de la CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Promedio de micrófono captura errores tiempo de secuencia marca, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Promedio de altavoz del destinatario de la llamada de representación errores de marca de tiempo de secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Modificador de voz es un modo de dúplex con capacidad de reducción de las interrupciones. Consulte la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causas de un evento de eco para el destinatario de la llamada. Consulte la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en secuencia de captura del micrófono del destinatario de la llamada. Si se usan auriculares con micrófono, el valor debe ser bajo.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en el destinatario de la llamada del envía la secuencia. Porcentaje de eco alta en enviar secuencias de una indicación de pérdida de eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Nivel de señal recibida en el servidor de mediación desde la puerta de enlace para el audio del destinatario de la llamada; Esto se aplica sólo al servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el intervalo aceptable debe ser [-30 a -18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Audio de nivel de señal recibida en el servidor de mediación desde la puerta de enlace para el destinatario de la llamada. Esto se aplica sólo al servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el intervalo aceptable debe ser menor que-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Automático control de ganancia (AGC) en el lado del servidor de mediación aplicado al audio del destinatario de la llamada.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Valor cuadrático medio (RMS) de la señal entrante para el destinatario de la llamada para los primeros 30 segundos de la llamada.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Relación media de muestras ocultas generadas por audio recuperación muestras típicas.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Relación media de muestras extendidas generadas por audio recuperación muestras típicas.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Relación media de muestras comprimidas generadas por audio recuperación muestras típicas.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tiempo de ida y vuelta desde las estadísticas de RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tiempo de ida y vuelta máximo para la secuencia de audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |Promedio de banda ancha MOS de red para la llamada. Esta métrica depende de la pérdida de paquetes, la vibración y el códec utilizado. Rango es 1.0 a 5.0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |Banda ancha mínimo MOS de red para la llamada.  <br/> |
|Valor de SendListenMOS  <br/> |decimal(3,2)  <br/> |Predicción de banda ancha MOS de escucha puntuación audio enviado, incluido el nivel de voz, el nivel de ruido y las características del dispositivo de captura.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |Valor de SendListenMOS mínimo para la llamada.  <br/> |
|Valor de RecvListenMOS  <br/> |decimal(3,2)  <br/> |Promedio de banda ancha prevista puntuación MOS de escucha audio recibido desde la red, incluido el nivel de voz, el nivel de ruido, códec, las condiciones de red y las características del dispositivo de captura.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |Valor de RecvListenMOS mínimo para la llamada.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica si se usó audio FEC para la llamada.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica la dirección de la afirmada identificar la información; 1 significa que la dirección de secuencia desde el autor de la llamada hasta el destinatario de la llamada; 0 indica que la dirección de secuencia desde el destinatario de la llamada al autor de la llamada.  <br/> |
   

