---
title: Vista de AudioStreamDetail
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
ms.openlocfilehash: 4dadc53f0641e2d59dc72b2add433c69fc9b8ad1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="audiostreamdetail-view"></a>Vista de AudioStreamDetail
 
La vista AudioStreamDetail almacena información acerca de cada secuencia de audio en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Id. único dentro de la línea media.  <br/> |
|Hora de inicio  <br/> |datetime  <br/> |Hora de inicio de la sesión.  <br/> |
|Hora de finalización  <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría del cuadro de diálogo: 0 es el Skype para Business Server pierna de servidor de mediación; 1 es el servidor de mediación para la pierna de puerta de enlace PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Marcador que indica si la llamada se ha omitido o no.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Si está presente, indica por qué una llamada no se ha omitido aunque identificadores correspondía a la omisión. Se define un solo valor:  <br/> 0 x 0001 - ID de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridad de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de llamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatario.  <br/> |
|Autor de llamada  <br/> |nvarchar(450)  <br/> |Llamador del identificador URI.  <br/> |
|Destinatario de la llamada  <br/> |nvarchar(450)  <br/> |Destinatario del identificador URI.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del llamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del llamador. Consulte la [tabla UserAgent](useragent.md) para obtener más detalles. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría de agente de usuario del llamador. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener más detalles. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del destinatario de la llamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener información. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría de agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener información. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del llamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del destinatario de la llamada.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Sistema operativo (OS) del extremo del llamador.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Sistema operativo (OS) del extremo del destinatario de la llamada.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Nombre de la CPU del extremo del llamador.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Nombre de la CPU del extremo del destinatario de la llamada.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU en el extremo del llamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU en el extremo del destinatario de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidad de procesador de la CPU del extremo del llamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidad de procesador de la CPU del extremo del destinatario de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del llamador se ejecuta en un entorno virtualizado. Consulte la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del destinatario de la llamada se ejecuta en un entorno virtualizado. Consulte la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|CorrelationKey  <br/> ||Clave de correlación. Referencia de la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Información sobre la ruta de los medios de comunicación, como directa o retransmitan. Consulte la [tabla de MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Ofrece información sobre el proceso de establecimiento interactivo de conectividad (ICE) en bits indicadores para el llamador. Para obtener información detallada, consulte la calidad de experiencia Supervisar servidor especificación del protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Ofrece información sobre el proceso de establecimiento interactivo de conectividad (ICE) en bits indicadores para el destinatario. Para obtener información detallada, consulte la calidad de experiencia Supervisar servidor especificación del protocolo.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte: 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP de la persona que llama. Esto puede ser tanto una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto utilizado por el llamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el llamador está dentro de la red de intervalo: 1 llamador de medios está dentro de la red empresarial, 0 significa que el llamador está fuera de la red.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Esto puede ser tanto una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto utilizado por el destinatario.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el destinatario está dentro de la red de intervalo: 1 destinatario de medios está dentro de la red empresarial, 0 significa que el destinatario está fuera de la red.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del llamador.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del llamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del destinatario de la llamada.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del destinatario de la llamada.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio V perimetral se utiliza por el llamador. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Puerto que se utiliza en el servicio V perimetral se utiliza por el llamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clave de la dirección IP del servicio V perimetral se utiliza por el destinatario. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto que se utiliza en el servicio V perimetral se utiliza por el destinatario.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del llamador.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de representación del llamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del llamador.  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de representación del llamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nombre del destinatario de la llamada del dispositivo de representación.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de render del destinatario de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del llamador: está conectado por cable de 0, 1 es inalámbrica.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el llamador conectados a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad de enlace de red para el extremo del llamador en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del destinatario: está conectado por cable de 0, 1 es inalámbrica.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el llamador conectados a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad de enlace de red para el extremo del destinatario de la llamada en bps.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS conversación de banda estrecha de las sesiones de audio (basadas en dos secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Ancho de banda real aplicada a la secuencia de lado de envío determinado dada las distintas configuraciones de directivas (TURN, API, SDP, Policy Server etc.). Esto no es debe confundirse con el ancho de banda eficaz porque puede haber un menor ancho de banda efectivo según la estimación del ancho de banda. Se trata, básicamente, el ancho de banda máximo que se puede tomar la secuencia de envío a excepción de los límites impuestos por la estimación del ancho de banda  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Vibración de red promedio de las estadísticas de protocolo de Control de tiempo Real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Velocidad de pérdida de paquetes promedio durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Pérdida de paquete máximo observada durante la llamada.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Densidad media de pérdida de paquetes durante las ráfagas de las pérdidas durante la llamada.  <br/> |
|BurstDuration  <br/> |int  <br/> |Duración media de pérdida de paquetes durante las ráfagas de las pérdidas durante la llamada.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Densidad media de pérdida de paquetes durante brechas entre ráfagas de pérdida de paquetes.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Duración media de los espacios entre ráfagas de pérdida de paquetes.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Recuento de paquetes para la secuencia de audio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimaciones de ancho de banda para la secuencia de audio.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red para la llamada entera. Rango es 0.0 a 5.0. Esta métrica muestra el importe que se ha reducido el MOS de red debido a la inestabilidad y pérdida de paquetes. Para una calidad aceptable debe menor que 0,5.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Degradación de red MOS máximo durante la llamada.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Degradación de la red MOS causada por vibración.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Degradación de la red MOS causada por la pérdida de paquetes.  <br/> |
|PayloadDescription  <br/> |int  <br/> |El códec de audio utilizado para la llamada, se hace referenciada en la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Tasa de muestreo de la secuencia de audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |El llamador envía a nivel de señal de audio de Control de ganancia posterior analógico para el audio. La unidad para que esta métrica es dBmo. Para obtener una calidad aceptable, debe ser al menos 30 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Nivel de señal de audio para el audio, el llamador recibe. La unidad para que esta métrica es dBmo. Para obtener una calidad aceptable, debe ser al menos 30 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |El llamador envía a nivel de ruido de audio Control de ganancia posterior a la analógica para el audio. La unidad para que esta métrica es dBmo. Para una calidad aceptable, debería ser inferior a 35 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Nivel de ruido de audio Control de ganancia posterior analógico para el audio, el llamador recibe. La unidad para que esta métrica es dBmo. Para una calidad aceptable, debería ser inferior a 35 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Eco devolver mejora pérdida para el llamador. La unidad para que esta métrica es dB. Los valores más bajos representan menos eco. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Problemas técnicos promedio por cinco minutos para la representación de altavoz del llamador. Para la buena calidad debe ser menor que una por cinco minutos. No informa A / teléfonos IP, servidores de mediación o servidores de conferencia V.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Capturan problemas técnicos promedio por cinco minutos para micrófono del llamador. Para la buena calidad debe ser menor que una por cinco minutos. No informa A / teléfonos IP, servidores de mediación o servidores de conferencia V.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Micrófono dispositivo deriva velocidad de reloj del llamador, con respecto al reloj de la CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Altavoz dispositivo deriva velocidad de reloj del llamador, con respecto al reloj de la CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Promedio de micrófono captura secuencia marca error de tiempo, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Promedio de altavoz del llamador de representación error de sello de tiempo de secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Modificador de voz es un modo semidúplex con posibilidad de reducción de las interrupciones. Consulte la [tabla de MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causas de evento eco para el llamador. Consulte la [tabla de MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en secuencia de captura de micrófono del llamador. Si se utilizan auriculares, el valor debe ser bajo.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en el llamador del envía la secuencia. Porcentaje de eco alta en enviar secuencias de una indicación de pérdida de eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Nivel de señal recibida en el servidor de mediación de la puerta de enlace para el audio del llamador; Esto se aplica sólo para el servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el rango aceptable debe ser -30 a-18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Audio de nivel de señal recibida en el servidor de mediación de la puerta de enlace para el llamador. Esto se aplica sólo para el servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el rango aceptable debe ser inferior a-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Automático de la ganancia (AGC) del control en el servidor de mediación aplicado al audio del llamador.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Raíz cuadrada Media (RMS) de la señal entrante al llamador para hasta los primeros 30 segundos de la llamada.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Representa el nivel de señal de audio analógica posteriores al Control de ganancia que el destinatario envía el audio. La unidad para que esta métrica es dBmo. Para obtener una calidad aceptable, debe ser al menos 30 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Nivel de señal de audio que el destinatario recibido el audio. La unidad para que esta métrica es dBmo. Para obtener una calidad aceptable, debe ser al menos 30 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Nivel de ruido de audio Control de ganancia posterior analógico para el audio, el destinatario enviado. La unidad para que esta métrica es dBmo. Para una calidad aceptable, debería ser inferior a 35 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Nivel de ruido de audio Control de ganancia posterior analógico que el destinatario recibido el audio. La unidad para que esta métrica es dBmo. Para una calidad aceptable, debería ser inferior a 35 dBmo. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Eco devolver mejora pérdida para el destinatario. La unidad para que esta métrica es dB. Los valores más bajos representan menos eco. Esta métrica no notifica el / los teléfonos IP o V Conferencing Server.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Problemas técnicos promedio por cinco minutos para la representación de altavoz del destinatario de la llamada. Para la buena calidad debe ser menor que una por cinco minutos. No informa A / teléfonos IP, servidores de mediación o servidores de conferencia V.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Capturan problemas técnicos promedio por cinco minutos para micrófono del destinatario de la llamada. Para la buena calidad debe ser menor que una por cinco minutos. No informa A / teléfonos IP, servidores de mediación o servidores de conferencia V.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Micrófono dispositivo deriva velocidad de reloj del destinatario, con respecto al reloj de la CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Altavoz dispositivo deriva velocidad de reloj del destinatario, con respecto al reloj de la CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Promedio de micrófono captura secuencia marca error de tiempo, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Promedio de altavoz del destinatario de la llamada de representación error de sello de tiempo de secuencia, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Modificador de voz es un modo semidúplex con posibilidad de reducción de las interrupciones. Consulte la [tabla de MediaLine](medialine-0.md) para obtener más información. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causas de evento eco para el destinatario. Consulte la [tabla de MediaLine](medialine-0.md) para obtener más información. <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en secuencia de captura de micrófono del destinatario de la llamada. Si se utilizan auriculares, el valor debe ser bajo.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta el eco en el destinatario del envía la secuencia. Porcentaje de eco alta en enviar secuencias de una indicación de pérdida de eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Nivel de señal recibida en el servidor de mediación de la puerta de enlace para el audio del destinatario de la llamada; Esto se aplica sólo para el servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el rango aceptable debe ser [-30 a -18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Audio de nivel de señal recibida en el servidor de mediación de la puerta de enlace para el destinatario. Esto se aplica sólo para el servidor de mediación. La unidad de esta métrica es dBoV. De buena calidad, el rango aceptable debe ser inferior a-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Automático de la ganancia (AGC) del control en el servidor de mediación aplicado al audio del destinatario de la llamada.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Raíz cuadrada Media (RMS) de la señal entrante al destinatario para hasta los primeros 30 segundos de la llamada.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Promedio de muestras ocultas generados por audio sanación a ejemplos típicos.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Promedio de muestras estiradas generados por audio sanación a ejemplos típicos.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Promedio de muestras comprimidas generado por audio sanación a ejemplos típicos.  <br/> |
|Ida y vuelta  <br/> |int  <br/> |Tiempo de ida y vuelta desde estadísticas RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tiempo de ida y vuelta máximo para la secuencia de audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |Promedio de banda ancha MOS de red para la llamada. Esta métrica depende de la pérdida de paquetes, la inestabilidad y el códec utilizado. Rango es 1.0 a 5.0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |Banda ancha mínimo MOS de red para la llamada.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |Promedio de predicción wideband puntuación MOS escuchando audio enviado, incluyendo el nivel de voz, ruido y las características del dispositivo de captura.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |SendListenMOS mínimo para la llamada.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |Puntuación de escucha MOS promedio wideband prevista para audio recibido de la red incluyendo el nivel de voz, nivel de ruido, códec, las condiciones de red y las características del dispositivo de captura.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |RecvListenMOS mínimo para la llamada.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica si se utilizó FEC de audio para la llamada.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica la dirección de la aserción p identificar información; 1 significa que la dirección de flujo es desde el llamador al destinatario; 0 significa que la dirección de flujo es del destinatario de la llamada al llamador.  <br/> |
   

