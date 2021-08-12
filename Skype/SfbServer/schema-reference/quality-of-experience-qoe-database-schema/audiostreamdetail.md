---
title: Vista AudioStreamDetail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: La vista AudioStreamDetail almacena información sobre cada secuencia de audio de la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 88300d4117a26dd033897d955ae82fb99f7d7b4878cb484caf4bae1fad3f965d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309189"
---
# <a name="audiostreamdetail-view"></a>Vista AudioStreamDetail
 
La vista AudioStreamDetail almacena información sobre cada secuencia de audio de la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |Entero  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |Entero  <br/> |Identificador único de una línea de medios.  <br/> |
|StartTime  <br/> |datetime  <br/> |Fecha y hora de inicio de la sesión.  <br/> |
|EndTime  <br/> |datetime  <br/> |Fecha y hora de finalización de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría de cuadro de diálogo: 0 es el Skype Empresarial Server al servidor de mediación; 1 es el servidor de mediación a la puerta de enlace RTC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Marca que indica si la llamada se omitió o no.  <br/> |
|MediaBypassWarningFlag  <br/> |Entero  <br/> |Si está presente, indica por qué no se omitió una llamada incluso si los IDs de omisión coincidían. Solo se define un valor:  <br/> 0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|CallPriority  <br/> |Entero  <br/> |Prioridad de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de autores de llamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatarios de llamadas.  <br/> |
|Caller  <br/> |nvarchar(450)  <br/> |URI del autor de la llamada.  <br/> |
|Destinatario de la llamada  <br/> |nvarchar(450)  <br/> |URI del destinatario de la llamada.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del autor de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo del agente de usuario del autor de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría del agente de usuario del autor de la llamada. Consulte la [tabla UserAgentDef (QoE) para](useragentdef-qoe.md) obtener más información. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del destinatario de la llamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener información. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría del agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener información. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del autor de la llamada.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del destinatario.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Sistema operativo (SO) del extremo del autor de la llamada.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Sistema operativo (SO) del extremo del destinatario.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Nombre de CPU del extremo del autor de la llamada.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Nombre de CPU del extremo del destinatario.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU en el extremo del autor de la llamada.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU en el extremo del destinatario de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |Entero  <br/> |Velocidad del procesador de CPU del punto de conexión del autor de la llamada.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |Entero  <br/> |Velocidad del procesador de CPU del punto de conexión del destinatario de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del autor de la llamada se está ejecutando en un entorno virtualizado. Consulte la [tabla Extremo para](endpoint.md) obtener más información. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado. Consulte la [tabla Extremo para](endpoint.md) obtener más información. <br/> |
|CorrelationKey  <br/> ||Clave de correlación. Se hace referencia a la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Información sobre la ruta de acceso multimedia, como directa o retransmitida. Vea la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerIceWarningFlags  <br/> |Entero  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|CalleeIceWarningFlags  <br/> |Entero  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte: 0 es UDP y 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |Entero  <br/> |Puerto del autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la red de intervalos: 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que el autor de la llamada está fuera de la red.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |Entero  <br/> |Puerto del destinatario de la llamada.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el destinatario está dentro de la red de intervalos: 1 significa que el destinatario está dentro de la red de empresa, 0 significa que el destinatario está fuera de la red.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nombre del sitio del autor de la llamada.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nombre del país o región del sitio del autor de la llamada.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nombre del sitio del destinatario.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nombre del país o región del sitio del destinatario.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Consulte la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CallerRelayPort  <br/> |Entero  <br/> |Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Consulte la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |Entero  <br/> |Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de representación del autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de representación del autor de la llamada.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de representación del destinatario de la llamada.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de representación del destinatario de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del autor de la llamada: 0 está cableada, 1 es inalámbrica.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el autor de la llamada se ha conectado a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad del vínculo de red del extremo del autor de la llamada en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del destinatario de la llamada: 0 está cableada, 1 es inalámbrica.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el autor de la llamada se ha conectado a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad de vínculo de red para el extremo del destinatario de la llamada en bps.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |Entero  <br/> |Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este es básicamente el ancho de banda máximo que la secuencia de envío puede tomar límites de limitación impuestos por la estimación de ancho de banda  <br/> |
|JitterInterArrival  <br/> |Entero  <br/> |Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |Entero  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Promedio de frecuencia de pérdida de paquetes durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Pérdida máxima de paquetes observada durante la llamada.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Densidad media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|BurstDuration  <br/> |Entero  <br/> |Duración media de la pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Densidad media de pérdida de paquetes durante los intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|BurstGapDuration  <br/> |Entero  <br/> |Duración media de los intervalos entre ráfagas de pérdida de paquetes.  <br/> |
|PacketUtilization  <br/> |Entero  <br/> |Recuento de paquetes para la secuencia de audio.  <br/> |
|BandwidthEst  <br/> |Entero  <br/> |Previsiones de ancho de banda de la secuencia de audio.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red para toda la llamada. El intervalo es de 0,0 a 5,0. Esta métrica muestra la cantidad que se redujo el MOS de red debido a la vibración y la pérdida de paquetes. Para una calidad aceptable debe ser inferior a 0,5.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Degradación máxima de MOS de red durante la llamada.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red causada por el jitter.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Degradación de MOS de red causada por la pérdida de paquetes.  <br/> |
|PayloadDescription  <br/> |Entero  <br/> |Códec de audio usado para la llamada, al que se hace referencia desde la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |Entero  <br/> |Velocidad de muestreo de la secuencia de audio.  <br/> |
|CallerSendSignalLevel  <br/> |Entero  <br/> |Nivel de señal de audio del control de ganancia posterior analógico para el audio enviado por el autor de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CallerRecvSignalLevel  <br/> |Entero  <br/> |Nivel de señal de audio para el audio que recibió el autor de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CallerSendNoiseLevel  <br/> |Entero  <br/> |Nivel de ruido de audio del control de ganancia posterior analógico para el audio enviado por el autor de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CallerRecvNoiseLevel  <br/> |Entero  <br/> |Nivel de ruido de audio del control de ganancia posterior analógico para el audio que recibió el autor de la llamada. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CallerEchoReturn  <br/> |Entero  <br/> |Mejora de pérdida de eco de devolución para el autor de la llamada. La unidad de esta métrica es dB. Los valores inferiores representan menos eco. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CallerSpeakerGlitchRate  <br/> |Entero  <br/> |Error promedio cada cinco minutos para la representación del altavoz del autor de la llamada. Para una buena calidad, debería ser inferior a uno por cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no notifican.  <br/> |
|CallerMicGlitchRate  <br/> |Entero  <br/> |Promedio de errores cada cinco minutos para la captura del micrófono del autor de la llamada. Para una buena calidad, esto debe ser inferior a uno por cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no notifican.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Velocidad de deriva del reloj del dispositivo del micrófono del autor de la llamada, en relación con el reloj de la CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Velocidad de deriva del reloj del dispositivo del altavoz del autor de la llamada, en relación con el reloj de la CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Error promedio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Promedio del error de marca de tiempo de secuencia de representación del orador del autor de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |El conmutador de voz es un modo semidúplex con capacidad de interrupción reducida. Vea la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causas de un evento de eco para el autor de la llamada. Vea la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo cuando se detecta eco en la secuencia de captura de micrófono del autor de la llamada. Si se usan auriculares, el valor debe ser bajo.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo en el que se detecta eco en la secuencia enviada del autor de la llamada. Alto porcentaje de eco en secuencias de envío una indicación de pérdida de eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |Entero  <br/> |Nivel de señal recibida en el servidor de mediación desde la puerta de enlace para el audio del autor de la llamada; esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser de -30 a -18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |Entero  <br/> |Nivel de señal recibido en el servidor de mediación desde la puerta de enlace para el audio del autor de la llamada. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser inferior a -50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |Entero  <br/> |Control automático de ganancia (AGC) en el lado servidor de mediación aplicado al audio del autor de la llamada.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Cuadrado medio raíz (RMS) de la señal entrante al autor de la llamada hasta los primeros 30 segundos de la llamada.  <br/> |
|CalleeSendSignalLevel  <br/> |Entero  <br/> |Representa el nivel de señal de audio del control de ganancia post analógico para el audio enviado por el destinatario. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CalleeRecvSignalLevel  <br/> |Entero  <br/> |Nivel de señal de audio para el audio que recibió el destinatario. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CalleeSendNoiseLevel  <br/> |Entero  <br/> |Nivel de ruido de audio del control de ganancia posterior analógico para el audio enviado por el destinatario. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CalleeRecvNoiseLevel  <br/> |Entero  <br/> |Nivel de ruido de audio del control de ganancia posterior analógico para el audio que recibió el destinatario. La unidad de esta métrica es dBmo. Para una calidad aceptable, debe ser inferior a 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CalleeEchoReturn  <br/> |Entero  <br/> |Mejora de pérdida de eco devuelto para el destinatario de la llamada. La unidad de esta métrica es dB. Los valores inferiores representan menos eco. El servidor de conferencia A/V o los teléfonos IP no notifican esta métrica.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |Entero  <br/> |Problemas promedio por cinco minutos para la representación del altavoz del destinatario. Para una buena calidad, debería ser inferior a uno por cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no notifican.  <br/> |
|CalleeMicGlitchRate  <br/> |Entero  <br/> |Error promedio por cinco minutos para la captura del micrófono del destinatario. Para una buena calidad, esto debe ser inferior a uno por cada cinco minutos. Los servidores de conferencia A/V, los servidores de mediación o los teléfonos IP no notifican.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Velocidad de deriva del reloj del dispositivo de micrófono del destinatario de la llamada, en relación con el reloj de CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Velocidad de deriva del reloj del dispositivo del altavoz del destinatario de la llamada, en relación con el reloj de CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Error promedio de marca de tiempo de captura de micrófono, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Promedio del error de marca de tiempo de secuencia de representación del orador del destinatario, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |El conmutador de voz es un modo semidúplex con capacidad de interrupción reducida. Vea la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causas de un evento de eco para el destinatario de la llamada. Vea la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo en el que se detecta eco en la secuencia de captura del micrófono del destinatario. Si se usan auriculares, el valor debe ser bajo.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentaje de tiempo en el que se detecta eco en la secuencia enviada del destinatario. Alto porcentaje de eco en secuencias de envío una indicación de pérdida de eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |Entero  <br/> |Nivel de señal recibido en el servidor de mediación desde la puerta de enlace para el audio del destinatario; esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser [-30 a -18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |Entero  <br/> |Nivel de señal recibido en el servidor de mediación desde la puerta de enlace para el audio del destinatario. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para una buena calidad, el intervalo aceptable debe ser inferior a -50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |Entero  <br/> |Control automático de ganancia (AGC) en el lado del servidor de mediación aplicado al audio del destinatario.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Cuadrado medio raíz (RMS) de la señal entrante al destinatario hasta los primeros 30 segundos de la llamada.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Relación media de muestras ocultas generadas por la recuperación de audio con las muestras típicas.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Relación media de muestras estiradas generadas por la recuperación de audio a muestras típicas.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Relación media de muestras comprimidas generadas por la recuperación de audio a muestras típicas.  <br/> |
|RoundTrip  <br/> |Entero  <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP.  <br/> |
|RoundTripMax  <br/> |Entero  <br/> |Tiempo de ida y vuelta máximo de la secuencia de audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |Promedio de MOS de red de banda ancha para la llamada. Esta métrica depende de la pérdida de paquetes, el vibración y el códec usados. El intervalo es de 1,0 a 5,0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |MOS de red de banda ancha mínima para la llamada.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |Puntuación media de MOS de escucha de banda ancha pronosticada para audio enviado, incluidos el nivel de voz, el nivel de ruido y las características del dispositivo de captura.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |SendListenMOS mínimo para la llamada.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |Puntuación media de MOS de escucha de banda ancha pronosticada para el audio recibido de la red, incluidos el nivel de voz, el nivel de ruido, el códec, las condiciones de red y las características del dispositivo de captura.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |Mínimo RecvListenMOS para la llamada.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica si se usó FEC de audio para la llamada.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica la dirección de la información de identificación afirmada por p; 1 significa que la dirección de la secuencia es del autor de la llamada al destinatario de la llamada; 0 significa que la dirección de la secuencia es del destinatario de la llamada al autor de la llamada.  <br/> |
   

