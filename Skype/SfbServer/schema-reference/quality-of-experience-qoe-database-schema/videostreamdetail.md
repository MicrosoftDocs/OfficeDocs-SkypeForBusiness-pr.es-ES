---
title: Vista VideoStreamDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: La vista VideoStreamDetail almacena información acerca de cada secuencia de vídeo en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6bafdbed3152bc73b2988e31877d8b7203557d46
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212000"
---
# <a name="videostreamdetail-view"></a>Vista VideoStreamDetail
 
La vista VideoStreamDetail almacena información acerca de cada secuencia de vídeo en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Descripción**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Identificador único dentro de una línea de medios.  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de inicio de la sesión.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del extremo del autor de la llamada.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del extremo del destinatario de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del extremo del autor de la llamada.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidad del procesador de CPU del extremo del destinatario de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema el autor de la llamada se está ejecutando en un entorno virtualizado. Vea la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado. Vea la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Información acerca de la ruta de medios, como directa o retransmitido. Consulte la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) describe en bits indicadores para el autor de la llamada. Para obtener información detallada, consulte la calidad de experiencia Monitoring Server especificación del protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) describe en bits indicadores para el destinatario de la llamada. Para obtener información detallada, consulte la calidad de experiencia Monitoring Server especificación del protocolo.  <br/> |
|Transport  <br/> |int  <br/> |Tipo de transporte: 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP del autor de la llamada. Esto puede resultar una IPv4 o una dirección IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto usado por el autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la red de la organización. 1 significa que es autor de la llamada dentro de la red de empresa, 0 significa que el autor de la llamada está fuera de la red.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Esto puede resultar una IPv4 o una dirección IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto usado por el destinatario de la llamada.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la organización red.1 significa que el destinatario de la llamada está dentro de la red de empresa, 0 significa que el destinatario está fuera de la red.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del autor de la llamada.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del autor de la llamada.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del destinatario de la llamada.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del destinatario de la llamada.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/v utilizado por el autor de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Puerto en el servicio perimetral A/v utilizado por el autor de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Tecla de dirección IP del servicio perimetral A/v que usa el destinatario de la llamada. Vea la [tabla IPAddress](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto en el servicio perimetral A/v que usa el destinatario de la llamada.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nombre del dispositivo de presentación de autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de presentación del autor de la llamada.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nombre del dispositivo de presentación del destinatario de la llamada.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de presentación del destinatario de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del autor de la llamada: 0 es cableada, 1 es inalámbrica.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el autor de la llamada se conectó a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Velocidad del vínculo de red de extremo del autor de la llamada en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del destinatario de la llamada: 0 es cableada, 1 es inalámbrica.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el destinatario de la llamada se conectó a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es diferente de VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad del vínculo de red de extremo del destinatario de la llamada (en bps).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basadas en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Ancho de banda real aplicada a la secuencia de lado de envío determinado dada distintas configuraciones de directivas (activar, API, SDP, servidor de directivas y así sucesivamente). Esto no es debe confundirse con el ancho de banda eficaz debido a que puede haber un ancho de banda eficaz inferior en función de la estimación del ancho de banda. Esto es, básicamente, el ancho de banda máximo que se puede realizar la secuencia de envío a excepción de los límites de impuestas por la estimación del ancho de banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Vibración de red promedio de las estadísticas del protocolo de Control de tiempo Real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tiempo de ida y vuelta desde las estadísticas de RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tiempo de ida y vuelta máximo para la secuencia de audio.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Frecuencia de pérdida de paquetes promedio durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Máximo la pérdida de paquetes observada durante la llamada.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo Real, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Previsiones de ancho de banda de la secuencia de audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Códec de audio utilizado para la llamada, de la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |Char (9)  <br/> |Resolución del vídeo en multiplicado por alto de píxeles de ancho de píxeles. El informe como una cadena.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Velocidad de bits Media de la secuencia de vídeo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Velocidad de fotogramas de vídeo recibida.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Velocidad de fotogramas de vídeo enviada.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Velocidad de bits de vídeo máxima durante la sesión de vídeo.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Tasa a la que se perdieron paquetes de vídeo.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Porcentaje del total de fotogramas de vídeo que se pierden.  <br/> |
|VideoFEC  <br/> |bit  <br/> |No se usa.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Cantidad promedio de ancho de banda asignado para vídeo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Porcentaje del total de fotogramas de vídeo que se perdió.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Dirección de secuencia para obtener información de identidad afirmada. 1 significa que la dirección de secuencia desde el autor de la llamada hasta el destinatario de la llamada; 0 indica que la dirección de secuencia desde el destinatario de la llamada al autor de la llamada.  <br/> |
   

