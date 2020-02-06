---
title: Vista AudioStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: La vista AudioStreamDetail almacena información acerca de cada secuencia de audio de la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 14815a107654fc83fc2b71c5070b82617154677c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810878"
---
# <a name="audiostreamdetail-view"></a>Vista AudioStreamDetail
 
La vista AudioStreamDetail almacena información acerca de cada secuencia de audio de la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Detalles**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |IDENTIFICADOR exclusivo dentro de una línea de medios.  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de inicio de la sesión.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoría de cuadro de diálogo: 0 es el segmento del servidor de Skype empresarial Server. 1 es el servidor de mediación para la puerta de la puerta de enlace RTC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Marcador que indica si la llamada se ha omitido o no.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Si está presente, indica por qué no se omitió una llamada aunque los identificadores de omisión coincidan. Solo se define un valor:  <br/> 0x0001: identificador de omisión desconocido para el adaptador de red predeterminado.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridad de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de llamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatarios de la llamada.  <br/> |
|Autor de llamada  <br/> |nvarchar (450)  <br/> |URI de la persona que llama.  <br/> |
|Destinatario de la llamada  <br/> |nvarchar (450)  <br/> |URI de la persona que llama.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo del agente de usuario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría del agente de usuario de la llamada. Para obtener más información, consulta la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario de la persona que llama.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener información. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoría del agente de usuario del destinatario de la llamada. Para obtener más información, consulta la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del punto de conexión de la llamada.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo de la persona que llama.  <br/> |
|CallerOS  <br/> |nvarchar(128  <br/> |Sistema operativo (SO) del punto final de la llamada.  <br/> |
|CalleeOS  <br/> |nvarchar(128  <br/> |Sistema operativo (SO) del extremo de la persona que llama.  <br/> |
|CallerCPUName  <br/> |nvarchar(128  <br/> |Nombre de la CPU del punto final de la llamada.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128  <br/> |Nombre de la CPU del punto final de la llamada.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU en el extremo de la persona que llama.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de la CPU en el punto final de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del punto final de la llamada.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del punto final de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado. Para obtener más información, consulte la [tabla de extremos](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado. Para obtener más información, consulte la [tabla de extremos](endpoint.md) . <br/> |
|CorrelationKey  <br/> ||Clave de correlación. Se hace referencia a ella desde la [tabla SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Información sobre la ruta multimedia, como Direct o retransmitida. Para obtener más información, consulte la [tabla MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte: 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto usado por el autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si la persona que llama está dentro de la red de intervalos: 1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Dirección IP del destinatario. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto usado por el destinatario.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el destinatario de la llamada está dentro de la red de intervalos: 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |Nombre del sitio de la persona que llama.  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |Nombre del país o de la región del sitio de la persona que llama.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |Nombre del sitio de la persona que llama.  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |Nombre del país o región del sitio de la persona que llama.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto usado en el servicio de borde A/V que usa el destinatario de la llamada.  <br/> |
|CallerCaptureDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de representación del autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de representación del autor de la llamada.  <br/> |
|CalleeCaptureDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de captura de la persona que llama.  <br/> |
|CalleeRenderDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de representación de la persona que llama.  <br/> |
|CalleeCaptureDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de captura.  <br/> |
|CalleeRenderDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de representación de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si la persona que llama se conecta a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es una VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal (18; 0)  <br/> |Velocidad de vínculo de red para el punto final de la llamada en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si la persona que llama se conecta a través de una red privada virtual: 1 es una red privada virtual (VPN), 0 no es una VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal (18; 0)  <br/> |Velocidad de vínculo de red para el punto final de la persona que llama en bps.  <br/> |
|ConversationalMOS  <br/> |decimal (3, 2)  <br/> |OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |El ancho de banda real aplicado a la transmisión de la parte de envío dada proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|PacketLossRate  <br/> |decimal (4,5)  <br/> |Tasa promedio de pérdida de paquetes durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal (4,5)  <br/> |Pérdida máxima de paquetes observadas durante la llamada.  <br/> |
|BurstDensity  <br/> |decimal (9, 4)  <br/> |Densidad promedio de pérdida de paquetes durante las ráfagas de pérdidas durante la llamada.  <br/> |
|BurstDuration  <br/> |int  <br/> |Duración media de pérdida de paquetes durante ráfagas de pérdidas durante la llamada.  <br/> |
|BurstGapDensity  <br/> |decimal (9, 4)  <br/> |Densidad media de pérdida de paquetes entre ráfagas de pérdida de paquetes.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Duración media de los huecos entre las ráfagas de pérdida de paquetes.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Recuento de paquetes de la secuencia de audio.  <br/> |
|Ancho de banda más  <br/> |int  <br/> |Cálculo de ancho de banda para la secuencia de audio.  <br/> |
|DegradationAvg  <br/> |decimal (3, 2)  <br/> |Degradación de MOS de red para toda la llamada. El intervalo está comprendido entre 0,0 y 5,0. Esta métrica muestra el monto que se redujo en el MOS de red debido a la vibración y a la pérdida de paquetes. Para una calidad aceptable, debe ser menor que 0,5.  <br/> |
|DegradationMax  <br/> |decimal (3, 2)  <br/> |La degradación de OP máxima de red durante la llamada.  <br/> |
|DegradationJitterAvg  <br/> |decimal (3, 2)  <br/> |Degradación de MOS de red causada por vibración.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal (3, 2)  <br/> |Degradación de MOS de red causada por pérdida de paquetes.  <br/> |
|PayloadDescription  <br/> |int  <br/> |El códec de audio usado para la llamada, al que se hace referencia desde la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Frecuencia de muestreo de la secuencia de audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Nivel posterior de señal de audio de control de ganancia analógica para el audio enviado por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Nivel de señal de audio del audio recibido por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |El nivel de ruido de audio de control de ganancia posterior analógico para el audio enviado por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |El nivel de ruido de audio de control de ganancia posterior analógico para el audio recibido por la persona que llama. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Return echo Return Enhancement para la persona que llama. La unidad para esta métrica es dB. Los valores más bajos representan menos eco. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Promedio de problemas por cinco minutos para la representación del altavoz de la persona que llama. Para obtener una buena calidad, debe ser inferior a un período de 5 minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Promedio de problemas por cinco minutos para la captura de micrófono de la persona que llama. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal (9; 2)  <br/> |Tasa de desplazamiento del reloj del dispositivo de la persona que llama, en relación con el reloj de la CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal (9; 2)  <br/> |Velocidad de desplazamiento del reloj del dispositivo de altavoz del autor de la llamada, relativa al reloj de la CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal (9; 2)  <br/> |Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal (9; 2)  <br/> |Promedio del error de marca de tiempo de la secuencia de representación de altavoces de la persona que llama, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Para obtener más información, consulte la [tabla MediaLine](medialine-0.md) . <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causas de un evento de Eco para el autor de la llamada. Para obtener más información, consulte la [tabla MediaLine](medialine-0.md) . <br/> |
|CallerEchoPercentMicIn  <br/> |decimal (4,5)  <br/> |Porcentaje de tiempo en que se detecta eco en el flujo de captura de micrófono de la persona que llama. Si se usa un auricular, el valor debe ser bajo.  <br/> |
|CallerEchoPercentSend  <br/> |decimal (4,5)  <br/> |Porcentaje de tiempo durante el que se detecta eco en el flujo enviado de la persona que llama. Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser de-30 a-18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Control automático de ganancia (AGC) en el servidor de mediación aplicado al audio de la persona que llama.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Cuadrado principal raíz (RMS) de la señal entrante al autor de la llamada durante los primeros 30 segundos de la llamada.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Representa el nivel de señal de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Nivel de señal de audio del audio recibido por el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe tener al menos 30 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |El nivel de ruido de audio de control de ganancia posterior analógico para el audio que envió el destinatario de la llamada. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |El nivel de ruido de audio de control de ganancia posterior analógico para el audio recibido. La unidad para esta métrica es dBmo. Para obtener una calidad aceptable, debe ser menor que 35 dBmo. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Return echo Return Enhancement para el destinatario de la llamada. La unidad para esta métrica es dB. Los valores más bajos representan menos eco. El servidor de conferencia A/V o los teléfonos IP no han informado de esta métrica.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Promedio de problemas por cinco minutos para la representación del altavoz de la persona que llama. Para obtener una buena calidad, debe ser inferior a un período de 5 minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Promedio de problemas por cinco minutos para la captura de micrófono de la persona que llama. Para obtener una buena calidad, debe ser inferior a uno por cinco minutos. No se han notificado por servidores de conferencia A/V, servidores de mediación o teléfonos IP.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal (9; 2)  <br/> |Tasa de desplazamiento del reloj del dispositivo de micrófono del destinatario, relativa al reloj de la CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal (9; 2)  <br/> |Tasa de desplazamiento del reloj del dispositivo de altavoz de la llamada, relativa al reloj de la CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal (9; 2)  <br/> |Error de marca de tiempo de captura de micrófono promedio, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal (9; 2)  <br/> |Promedio del error de marca de tiempo del altavoz del destinatario de la llamada, en milisegundos, en los últimos 20 segundos de la llamada.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |El cambio de voz es un modo de dúplex medio con una capacidad de interrupción reducida. Para obtener más información, consulte la [tabla MediaLine](medialine-0.md) . <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causas de un evento de Eco para el destinatario de la llamada. Para obtener más información, consulte la [tabla MediaLine](medialine-0.md) . <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal (4,5)  <br/> |Porcentaje de tiempo durante el que se detecta eco en el flujo de captura de micrófono de la persona que llama. Si se usa un auricular, el valor debe ser bajo.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal (4,5)  <br/> |Porcentaje de tiempo durante el que se detecta eco en el flujo enviado de la persona que llama. Porcentaje de eco alto en secuencias de envío indica una pérdida de eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama; Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser [-30 a-18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Nivel de señal recibido en el servidor de mediación de la puerta de enlace para el audio de la persona que llama. Esto solo se aplica al servidor de mediación. La unidad de esta métrica es dBoV. Para obtener una buena calidad, el rango aceptable debe ser menor que-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Control automático de ganancia (AGC) en el servidor de mediación aplicado al audio de la persona que llama.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Cuadrado de la media raíz (RMS) de la señal entrante para el destinatario durante los primeros 30 segundos de la llamada.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal (4,5)  <br/> |Relación media entre las muestras ocultas generadas por la corrección de audio a muestras típicas.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal (4,5)  <br/> |Relación media de muestras extendidas generadas por la recuperación de audio a muestras típicas.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal (4,5)  <br/> |Relación media de muestras comprimidas generadas por la corrección de audio a muestras típicas.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tiempo máximo de ida y vuelta para la secuencia de audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal (3, 2)  <br/> |MOS de red de banda ancha promedio para la llamada. Esta métrica depende de la pérdida del paquete, de la vibración y del códec usado. El intervalo está comprendido entre 1,0 y 5,0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal (3, 2)  <br/> |MOS de red de banda ancha mínima para la llamada.  <br/> |
|SendListenMOS  <br/> |decimal (3, 2)  <br/> |Puntuación de MOS de escucha de banda ancha prevista para el audio enviado, incluyendo el nivel de voz, el nivel de ruido y las características del dispositivo de captura.  <br/> |
|SendListenMOSMin  <br/> |decimal (3, 2)  <br/> |SendListenMOS mínimo para la llamada.  <br/> |
|RecvListenMOS  <br/> |decimal (3, 2)  <br/> |Puntuación de MOS de escucha de banda ancha prevista para el audio recibido de la red, incluido el nivel de voz, nivel de ruido, códec, condiciones de red y características de dispositivo de captura.  <br/> |
|RecvListenMOSMin  <br/> |decimal (3, 2)  <br/> |RecvListenMOS mínimo para la llamada.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica si se usó el audio FEC para la llamada.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica la dirección de la información identificada por p; 1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada. 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.  <br/> |
   

