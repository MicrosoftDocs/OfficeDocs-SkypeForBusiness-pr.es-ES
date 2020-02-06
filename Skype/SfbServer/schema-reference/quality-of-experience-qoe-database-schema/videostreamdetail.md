---
title: Vista VideoStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: La vista VideoStreamDetail almacena información acerca de cada secuencia de vídeo de la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 3fb598feec3b4dca87086504c620109a99bce7d0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804150"
---
# <a name="videostreamdetail-view"></a>Vista VideoStreamDetail
 
La vista VideoStreamDetail almacena información acerca de cada secuencia de vídeo de la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Descripción**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Se hace referencia a ella desde la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |IDENTIFICADOR exclusivo dentro de una línea de medios.  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de inicio de la sesión.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridad de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de llamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatarios de la llamada.  <br/> |
|Autor de llamada  <br/> |nvarchar (450)  <br/> |URI de la persona que llama.  <br/> |
|Destinatario de la llamada  <br/> |nvarchar (450)  <br/> |URI de la persona que llama.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario de la llamada. Consulte la [tabla UserAgent](useragent.md) para obtener más información. <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del punto final de la llamada.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del punto final de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del punto final de la llamada.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del punto final de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado. Para obtener más información, consulte la [tabla de extremos](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema de la persona que llama se está ejecutando en un entorno virtualizado. Para obtener más información, consulte la [tabla de extremos](endpoint.md) . <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Información sobre la ruta multimedia, como Direct o retransmitida. Para obtener más información, consulte la [tabla MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en indicadores de bits para la persona que llama. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento de conectividad interactiva (ICE) descrito en marcas de bits para el destinatario de la llamada. Para obtener más información, consulte la especificación de protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|Transport  <br/> |int  <br/> |Tipo de transporte: 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto usado por el autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si la persona que llama está dentro de la red de la organización. 1 significa que la persona que llama está dentro de la red de la empresa, 0 significa que la persona que llama está fuera de la red.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Dirección IP del destinatario. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto usado por el destinatario.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si la persona que llama está dentro de la red de la organización. 1 significa que el destinatario de la llamada está dentro de la red de la empresa, 0 significa que el destinatario de la llamada está fuera de la red.  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |Nombre del sitio de la persona que llama.  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |Nombre del país o de la región del sitio de la persona que llama.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |Nombre del sitio de la persona que llama.  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |Nombre del país o región del sitio de la persona que llama.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Puerto en el servicio perimetral A/V usado por el autor de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Para obtener más información, consulte la [tabla dirección IP](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto del servicio perimetral A/V usado por el destinatario de la llamada.  <br/> |
|CallerCaptureDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de representación del autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de representación del autor de la llamada.  <br/> |
|CalleeCaptureDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de captura de la persona que llama.  <br/> |
|CalleeRenderDev  <br/> |VARCHAR (256)  <br/> |Nombre del dispositivo de representación de la persona que llama.  <br/> |
|CalleCaptureDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de captura.  <br/> |
|CalleeRenderDevDriver  <br/> |VARCHAR (256)  <br/> |Nombre del controlador del dispositivo de representación de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el autor de la llamada se ha conectado a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal (18;)  <br/> |Velocidad de vínculo de red para el punto final de la llamada en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red de la persona que llama: 0 es con cable, 1 es inalámbrico.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el destinatario de la llamada se conecta a través de una red privada virtual. 1 es una red privada virtual (VPN) y 0 no es una VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal (18; 0)  <br/> |Velocidad de vínculo de red del extremo de la persona que llama (en bps).  <br/> |
|ConversationalMOS  <br/> |decimal (3, 2)  <br/> |OP de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |El ancho de banda real aplicado a la transmisión de la parte de envío dada proporciona varias configuraciones de directiva (TURN, API, SDP, Policy Server, etc.). Esto no se debe confundir con el ancho de banda efectivo porque puede haber un ancho de banda más bajo según el cálculo de ancho de banda. Básicamente, este es el ancho de banda máximo que la secuencia de envío puede tomar límites de bloqueo impuestas por la estimación del ancho de banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Vibración de red media de las estadísticas del Protocolo de control de tiempo real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tiempo máximo de ida y vuelta para la secuencia de audio.  <br/> |
|PacketLossRate  <br/> |decimal (4,5)  <br/> |Tasa promedio de pérdida de paquetes durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal (4,5)  <br/> |Pérdida máxima de paquetes observadas durante la llamada.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).  <br/> |
|Ancho de banda más  <br/> |int  <br/> |Cálculo de ancho de banda para la secuencia de audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Códec de audio usado para la llamada, al que se hace referencia desde la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|Resolución de la  <br/> |carácter (9)  <br/> |Resolución del vídeo en píxeles ancho multiplicado por píxeles alto. Se ha notificado como una cadena.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Promedio de velocidad de bits de la secuencia de vídeo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal (9, 4)  <br/> |Velocidad de fotogramas de video recibido.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal (9, 4)  <br/> |Velocidad de fotogramas enviada.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Máxima tasa de bits de vídeo durante la sesión de video.  <br/> |
|Tasa  <br/> |decimal (9, 4)  <br/> |Velocidad a la que se han perdido paquetes de video.  <br/> |
|VideoFrameLossRate  <br/> |decimal (9.4)  <br/> |Porcentaje de fotogramas de video totales que se pierden.  <br/> |
|VideoFEC  <br/> |bit  <br/> |No usado.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Cantidad promedio de ancho de banda asignado para el vídeo.  <br/> |
|Media  <br/> |decimal (9.4)  <br/> |Porcentaje de fotogramas de video totales que se han perdido.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Dirección de la secuencia para la información de identidad declarada en p. 1 significa que la dirección de la transmisión es de la persona que llama al destinatario de la llamada. 0 significa que la dirección de la transmisión es de la persona que llama a la persona que llama.  <br/> |
   

