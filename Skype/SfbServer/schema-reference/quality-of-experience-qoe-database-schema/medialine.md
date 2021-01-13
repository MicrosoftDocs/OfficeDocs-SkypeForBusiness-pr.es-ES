---
title: Vista MediaLine
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
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La vista MediaLine almacena información acerca de cada línea de medios de la base de datos. Una sesión de audio normalmente contiene una línea de medios de audio. Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c31fe1c5b8f6ed97d49c695986ad14fd890ae26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802750"
---
# <a name="medialine-view"></a>Vista MediaLine
 
La vista MediaLine almacena información acerca de cada línea de medios de la base de datos. Una sesión de audio normalmente contiene una línea de medios de audio. Una sesión de audio y vídeo (A/V) suele contener una línea de medios de audio y una línea de medios de vídeo, aunque la sesión podría contener dos líneas de medios de vídeo si se usa un dispositivo de conferencias o si se usa la vista de galería. Esta vista se introdujo en Microsoft Lync Server 2013.
  
|**Columna**|**Tipo de datos**|**details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |entero  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Se hace referencia desde la [tabla MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |entero  <br/> |Información sobre el proceso de establecimiento interactivo de conectividad (ICE) descrito en bits de indicador para el autor de la llamada. Si desea obtener información detallada, consulte la Especificación del protocolo de servidor de supervisión de la calidad de la experiencia.  <br/> |
|CalleeIceWarningFlags  <br/> |entero  <br/> |Información acerca del proceso de establecimiento interactivo de conectividad (ICE), proceso descrito en indicadores de bits para el destinatario de la llamada. Para obtener detalles, consulte el protocolo de servidor de supervisión de calidad de experiencia.  <br/> |
|Seguridad  <br/> |tinyint  <br/> |Perfil de seguridad en uso. 0 es NONE, 1 es SRTP, 2 es V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte. 0 es UDP, 1 es TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Dirección IP del autor de la llamada. Esta puede ser una dirección IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |entero  <br/> |Puerto del autor de la llamada.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica si el autor de la llamada está o no dentro de la red la organización. 1 significa que el autor de la llamada se encuentra dentro de la red de empresa. 0 significa que el autor de la llamada se encuentra fuera de la red.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |Dirección MAC de la interfaz de red usada por el autor de la llamada.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/V que usa el autor de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|CalleeRelayPort  <br/> |entero  <br/> |Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.  <br/> |
|CallerReiveiveIPAddr  <br/> |var(50)  <br/> |Dirección IP del autor de la llamada según lo notificado por el servicio perimetral A/V. Esta dirección puede ser diferente de CallerIPAddr si el cliente se encuentra detrás de una NAT por ejemplo.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de representación del autor de la llamada.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de captura del autor de la llamada.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de representación del autor de la llamada.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar(256  <br/> |Descripción del controlador Wifi del autor de la llamada.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Versión del controlador Wifi del autor de la llamada.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Detalles de la conexión de red del autor de la llamada. Vea la [tabla NetworkConnectionDetail](networkconnectiondetail.md) para obtener más información. <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |Identificador de conjunto de servicio básico usado por conexión WiFi de autores de llamada.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica si el autor de llamada se conectó a través de una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Dirección IP del destinatario de la llamada. Esta puede ser una dirección IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |entero  <br/> |Puerto del destinatario de la llamada.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica si el autor de la llamada se encuentra dentro de la red de empresa. 1 significa el destinatario de la llamada dentro de la red de empresa, 0 significa el destinatario de la llamada fuera de la red.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |Dirección MAC de la interfaz de red usada por el destinatario de la llamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Dirección IP del servicio perimetral A/V usado por el autor de la llamada. Vea la [tabla IPAddress para](ipaddress.md) obtener más información. <br/> |
|CalleeRelayPort  <br/> |entero  <br/> |Puerto usado en el servicio perimetral A/V usado por el autor de la llamada.  <br/> |
|CalleeReiveIPAddr  <br/> |var(50)  <br/> |La dirección IP del destinatario de la llamada según lo notificado por el servicio perimetral A/V. Esta dirección puede ser diferente de CalleeIPAddr si el cliente se encuentra detrás de un NAT, por ejemplo.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nombre del dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nombre del dispositivo de representación del destinatario de la llamada.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de captura del destinatario de la llamada.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nombre del controlador del dispositivo de representación del destinatario de la llamada.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Descripción del controlador Wifi del destinatario de la llamada.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar(256  <br/> |Versión del controlador Wifi del destinatario de la llamada.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Detalles de la conexión de red del destinatario de la llamada. Vea la [tabla NetworkConnectionDetail](networkconnectiondetail.md) para obtener más información. <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Identificador del conjunto de servicios básico usado por la conexión WiFi del destinatario de la llamada.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica si el destinatario de la llamada se conectó por una red privada virtual. 1 hace referencia a red privada virtual (VPN), 0 hace referencia a red diferente de VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS de conversación de banda estrecha de las sesiones de audio (basado en ambas secuencias de audio).  <br/> |
|AppliedBandwidthLimit  <br/> |entero  <br/> |Este es el ancho de banda real aplicado a la secuencia de envío determinada en un entorno regido por diversas directivas (TURN, API, SDP, Servidor de directivas, etc.). No se debe confundir con el ancho de banda efectivo, ya que el ancho de banda efectivo puede ser menor en función de las previsiones de ancho de banda. Este valor es, a grandes rasgos, el ancho de banda máximo que la secuencia de envío puede ocupar asumiendo los límites impuestos por la previsión de ancho de banda.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Origen del límite de ancho de banda impuesto. Describe de dónde viene el límite de ancho de banda (por ejemplo, "Servidor de directivas", "Servidor TURN" o "Modalidad").  <br/> |
|Caller  <br/> |bit  <br/> |Indica si se han recibido las métricas del autor de la llamada. 1 indica que sí, 0 que no.  <br/> |
|Destinatario de la llamada  <br/> |bit  <br/> |Indica si se han recibido las métricas del destinatario de la llamada. 1 indica que sí, 0 que no.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica si el informe es para una parte de la llamada o para la llamada completa.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica si una llamada se clasificó como deficiente (1) o como llamada correcta (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica si el autor de llamada se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica si el usuario llamado se conectó a la red con el protocolo de establecimiento interactivo de conectividad (ICE)  <br/> |
   

