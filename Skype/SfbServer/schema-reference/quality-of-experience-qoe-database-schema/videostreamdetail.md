---
title: Vista VideoStreamDetail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: La vista VideoStreamDetail almacena información de todas las secuencias de vídeo en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6341febeb8d43e36975c5b4cc446ac24ff1287c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834350"
---
# <a name="videostreamdetail-view"></a>Vista VideoStreamDetail
 
La vista VideoStreamDetail almacena información de todas las secuencias de vídeo en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**Descripción**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |entero  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |entero  <br/> |Identificador único de una línea de medios.  <br/> |
|StartTime  <br/> |datetime  <br/> |Fecha y hora de inicio de la sesión.  <br/> |
|EndTime  <br/> |datetime  <br/> |Fecha y hora de finalización de la sesión.  <br/> |
|CallPriority  <br/> |entero  <br/> |Prioridad de la llamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de autores de llamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del grupo de destinatarios de llamadas.  <br/> |
|Caller  <br/> |nvarchar(450)  <br/> |URI del autor de la llamada.  <br/> |
|Destinatario de la llamada  <br/> |nvarchar(450)  <br/> |URI del destinatario de la llamada.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del autor de la llamada.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del autor de la llamada. Consulte la [tabla UserAgent para](useragent.md) obtener más información. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría del agente de usuario del autor de la llamada. Consulte la [tabla UserAgentDef (QoE) para](useragentdef-qoe.md) obtener más información. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadena de agente de usuario del destinatario de la llamada.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuario del destinatario de la llamada. Vea la [tabla UserAgent](useragent.md) para obtener información. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoría del agente de usuario del destinatario de la llamada. Consulte la [tabla UserAgentDef (QoE)](useragentdef-qoe.md) para obtener información. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del autor de la llamada.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nombre del extremo del destinatario de la llamada.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Sistema operativo (SO) del extremo del autor de la llamada.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Sistema operativo (SO) del extremo del destinatario de la llamada.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Nombre de CPU del extremo del autor de la llamada.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Nombre de CPU del punto de conexión del destinatario de la llamada.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del extremo del autor de la llamada.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU del extremo del destinatario de la llamada.  <br/> |
|CallerCPUProcessorSpeed  <br/> |entero  <br/> |Velocidad del procesador de CPU del punto de conexión del autor de la llamada.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |entero  <br/> |Velocidad del procesador de CPU del punto de conexión del destinatario de la llamada.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del autor de la llamada se está ejecutando en un entorno virtualizado. Consulta la [tabla Endpoint para](endpoint.md) obtener más información. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica si el sistema del destinatario de la llamada se está ejecutando en un entorno virtualizado. Consulta la [tabla Endpoint para](endpoint.md) obtener más información. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Información sobre la ruta de medios, como directa o retransmitida. Consulta la [tabla MediaLine](medialine-0.md) para obtener más información. <br/> |
|CallerIceWarningFlags  <br/> |entero  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|CalleeIceWarningFlags  <br/> |entero  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el destinatario de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|Transport  <br/> |entero  <br/> |Tipo de transporte: 0 es UDP y 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP del autor de la llamada. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |entero  <br/> |Puerto del autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el autor de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Puede ser una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |entero  <br/> |Puerto del destinatario de la llamada.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el autor de la llamada está dentro de la red de la organización. El valor 1 significa que el destinatario de la llamada está dentro de la red de empresa, 0 significa que se encuentra fuera.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nombre del sitio del autor de la llamada.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nombre del país o región del sitio del autor de la llamada.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nombre del sitio del destinatario de la llamada.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nombre del país o región del sitio del destinatario de la llamada.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|CallerRelayPort  <br/> |entero  <br/> |Puerto en el servicio perimetral A/V que usa el autor de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clave de dirección IP del servicio perimetral A/V que usa el destinatario de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|CalleeRelayPort  <br/> |entero  <br/> |Puerto en el servicio perimetral A/V que usa el destinatario de la llamada.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de representación del autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de representación del autor de la llamada.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de representación del destinatario de la llamada.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de representación del destinatario de la llamada.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del autor de la llamada: 0 está cableado, 1 es inalámbrico.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el autor de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Velocidad del vínculo de red del extremo del autor de la llamada en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexión de red del destinatario de la llamada: 0 está cableado, 1 es inalámbrico.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el destinatario de la llamada está conectado a través de una red privada virtual. El valor 1 indica una red privada virtual (VPN) y 0, otra red diferente.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidad de vínculo de red para el extremo del destinatario de la llamada (en bps).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |entero  <br/> |Ancho de banda real aplicado a una secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.  <br/> |
|JitterInterArrival  <br/> |entero  <br/> |Promedio de vibración de red de las estadísticas de Protocolo de control en tiempo real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |entero  <br/> |Vibración máxima de la red durante la llamada.  <br/> |
|RoundTrip  <br/> |entero  <br/> |Tiempo de ida y vuelta de las estadísticas de RTCP.  <br/> |
|RoundTripMax  <br/> |entero  <br/> |Tiempo de ida y vuelta máximo de la secuencia de audio.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Promedio de frecuencia de pérdida de paquetes durante la llamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Pérdida máxima de paquetes observada durante la llamada.  <br/> |
|PacketUtilization  <br/> |entero  <br/> |Número de paquetes de la secuencia de vídeo (Protocolo de transporte en tiempo real, RTP).  <br/> |
|BandwidthEst  <br/> |entero  <br/> |Previsiones de ancho de banda de la secuencia de audio.  <br/> |
|PayloadDescription  <br/> |entero  <br/> |Códec de audio usado para la llamada, al que se hace referencia desde la [tabla PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Resolución del vídeo en píxeles de ancho multiplicados por píxeles de alto. Se proporciona como cadena.  <br/> |
|VideoBitRateAvg  <br/> |entero  <br/> |Tasa de bits media de la secuencia de vídeo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Tasa de fotogramas de vídeo recibida.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Tasa de fotogramas de vídeo enviada.  <br/> |
|ViideoBitRateMax  <br/> |entero  <br/> |Tasa de bits de vídeo máxima durante la sesión de vídeo.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Tasa a la que se perdieron los paquetes de vídeo.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Porcentaje del total de fotogramas de vídeo que se pierde.  <br/> |
|VideoFEC  <br/> |bit  <br/> |No se usa.  <br/> |
|VideoAllocateBWAvg  <br/> |entero  <br/> |Cantidad máxima del ancho de banda asignada para vídeo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Porcentaje del total de fotogramas de vídeo que se perdió.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Dirección de secuencia de la información de identidad p-asserted. El valor 1 indica que la dirección de la secuencia es del autor de la llamada al destinatario; y 0 significa del destinatario al autor.  <br/> |
   

