---
title: Vista de VideoStreamDetail
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
ms.openlocfilehash: d102a5e99cfcecb7d5e2e35b113e13509662af4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="videostreamdetail-view"></a>Vista de VideoStreamDetail
 
La vista VideoStreamDetail almacena información acerca de cada secuencia de vídeo en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Descripción**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referencia de la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Id. único dentro de la línea media.  <br/> |
|Hora de inicio  <br/> |datetime  <br/> |Hora de inicio de la sesión.  <br/> |
|Hora de finalización  <br/> |datetime  <br/> |Hora de finalización de la sesión.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del extremo del llamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del extremo del destinatario de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidad de procesador de la CPU del extremo del llamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidad de procesador de la CPU del extremo del destinatario de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del llamador se ejecuta en un entorno virtualizado. Consulte la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del destinatario de la llamada se ejecuta en un entorno virtualizado. Consulte la [tabla de extremo](endpoint.md) para obtener más información. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Información sobre la ruta de acceso de medios, como directa o retransmitan. Consulte la [tabla de MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Ofrece información sobre el proceso de establecimiento interactivo de conectividad (ICE) en bits indicadores para el llamador. Para obtener información detallada, consulte la calidad de experiencia Supervisar servidor especificación del protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Ofrece información sobre el proceso de establecimiento interactivo de conectividad (ICE) en bits indicadores para el destinatario. Para obtener información detallada, consulte la calidad de experiencia Supervisar servidor especificación del protocolo.  <br/> |
|Transport  <br/> |int  <br/> |Tipo de transporte: 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP de la persona que llama. Esto puede ser tanto una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Puerto utilizado por el llamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el llamador está dentro de la red de la organización. 1 significa llamador está dentro de la red empresarial, 0 significa que el llamador está fuera de la red.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Esto puede ser tanto una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Puerto utilizado por el destinatario.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica que si el llamador está dentro de la organización de red.1 significa destinatario está dentro de la red empresarial, 0 significa que el destinatario está fuera de la red.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del llamador.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del llamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nombre del sitio del destinatario de la llamada.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nombre del país o región del sitio del destinatario de la llamada.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio V perimetral se utiliza por el llamador. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Puerto en el servicio V perimetral se utiliza por el llamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clave de la dirección IP del servicio V perimetral se utiliza por el destinatario. Consulte la [tabla de dirección IP](ipaddress.md) para obtener más información. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Puerto en el servicio V perimetral se utiliza por el destinatario.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del llamador.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de representación del llamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del llamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de representación del llamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nombre de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nombre del destinatario de la llamada del dispositivo de representación.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nombre de controlador de dispositivo de render del destinatario de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del llamador: está conectado por cable de 0, 1 es inalámbrica.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si se permite o no el llamador conectado a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Velocidad de enlace de red para el extremo del llamador en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del destinatario: está conectado por cable de 0, 1 es inalámbrica.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si se permite o no el destinatario conectados a través de una red privada virtual. 1 es una red privada virtual (VPN), 0 es no VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad de enlace de red para el extremo del destinatario (en bps).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS conversación de banda estrecha de las sesiones de audio (basadas en dos secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Ancho de banda real aplicada a la secuencia de lado de envío determinado dada las distintas configuraciones de directivas (TURN, API, SDP, Policy Server etc.). Esto no es debe confundirse con el ancho de banda eficaz porque puede haber un menor ancho de banda efectivo según la estimación del ancho de banda. Se trata, básicamente, el ancho de banda máximo que se puede tomar la secuencia de envío a excepción de los límites impuestos por la estimación del ancho de banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Vibración de red promedio de las estadísticas de protocolo de Control de tiempo Real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|Ida y vuelta  <br/> |int  <br/> |Tiempo de ida y vuelta desde estadísticas RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tiempo de ida y vuelta máximo para la secuencia de audio.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Velocidad de pérdida de paquetes promedio durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Pérdida de paquete máximo observada durante la llamada.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Recuento de paquetes para la secuencia de vídeo (Protocolo de transporte en tiempo Real, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimaciones de ancho de banda para la secuencia de audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Códec de audio utilizado para la llamada, se hace referenciada en la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |Char (9)  <br/> |Resolución del vídeo en el ancho de píxeles multiplicado por alto de píxeles. El informe como una cadena.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Velocidad promedio de bits de la secuencia de vídeo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Velocidad de fotogramas de vídeo recibido.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Velocidad de fotogramas de vídeo enviado.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Velocidad de bits de vídeo máxima durante la sesión de video.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Velocidad a la que se han perdido paquetes de video.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Porcentaje total de cuadros de vídeo que se pierden.  <br/> |
|VideoFEC  <br/> |bit  <br/> |No se utiliza.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Cantidad promedio de ancho de banda asignado para el vídeo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Porcentaje total de cuadros de vídeo que se han perdido.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Dirección de flujo para la información de identidad afirmado p. 1 significa que la dirección de flujo es desde el llamador al destinatario; 0 significa que la dirección de flujo es del destinatario de la llamada al llamador.  <br/> |
   

